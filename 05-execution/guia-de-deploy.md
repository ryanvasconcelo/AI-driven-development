# GUIA DE DEPLOY — PROTOCOLO ANTI-FALHA DE PRODUCAO (SOP-IA v2.0)

## O que e
Um roteiro estruturado e sequencial para realizar deploys com zero ambiguidade. Resolve
o problema mais comum em pequenos times: o sistema funciona perfeitamente em
desenvolvimento e quebra em producao por problemas de variaveis de ambiente, URL hardcoded,
configuracoes esquecidas e diferencas de contexto.

## Por que existe
Um deploy nao e apenas enviar codigo para um servidor. E um processo de transicao de
contexto. O codigo sai de um ambiente onde o desenvolvedor controla tudo (localhost,
variaveis locais, banco de dev) para um ambiente compartilhado, com restricoes de
seguranca, redes diferentes e dependencias externas reais.
Cada diferenca entre esses dois contextos e um ponto potencial de falha.

## Nivel de Maturidade Minimo: 2
## Modo de Operacao: Todos (o deploy e critico independente do tamanho do time)

---

## Os 7 Motivos Mais Comuns de Falha em Deploy

1. Variavel de ambiente nao definida no servidor de producao
2. URL hardcoded apontando para localhost ou ambiente de dev
3. Porta ou protocolo diferente (http vs https, porta 3000 vs 443)
4. Banco de dados de producao com schema desatualizado (migracao esquecida)
5. Permissao de CORS nao configurada para o dominio de producao
6. Dependencia instalada localmente mas nao listada no package.json
7. Build gerado em maquina local com variaveis de dev embutidas

---

## Pre-Deploy: Checklist de Ambiente (Executar Sempre)

### Bloco 1 — Variaveis de Ambiente
- [ ] Existe um arquivo `.env.example` commitado no repositorio com TODAS as variaveis necessarias?
- [ ] O arquivo `.env` real esta no `.gitignore` e NUNCA foi commitado?
- [ ] Cada variavel do `.env.example` tem uma entrada correspondente no painel do servidor
  de producao (Vercel, Railway, AWS, etc.)?
- [ ] Variaveis que mudam entre ambientes (URLs de API, chaves de banco) usam o prefixo
  correto do framework (ex: `VITE_` para Vite, `NEXT_PUBLIC_` para Next.js)?
- [ ] Foi feita uma comparacao linha a linha entre o `.env.example` e as variaveis
  cadastradas no servidor de producao antes deste deploy?

### Bloco 2 — URLs e Endpoints
- [ ] Existe busca por "localhost" em todo o codebase? (grep -r "localhost" src/)
  Se encontrado: avaliar cada ocorrencia. Se for constante de desenvolvimento, mover para variavel de ambiente.
- [ ] Existe busca por portas hardcoded (":3000", ":5432", ":8080") no codigo de producao?
- [ ] As chamadas de API usam uma variavel de ambiente para a URL base, nao uma string fixa?
- [ ] Os redirects de autenticacao (OAuth, login) apontam para o dominio de producao correto?
- [ ] Os corsOrigins do backend incluem o dominio de producao atual?

### Bloco 3 — Build e Dependencias
- [ ] O comando de build executa sem erros em maquina limpa?
  (Testar em branch separada ou via CI/CD sem cache)
- [ ] Todas as dependencias usadas estao listadas em `dependencies` (nao apenas em `devDependencies`)?
- [ ] Se houver dependencias de sistema (Python, Node versao especifica), estao documentadas?
- [ ] O `.nvmrc` ou `engines` no `package.json` especifica a versao exata de Node usada?

### Bloco 4 — Banco de Dados e Persistencia
- [ ] Existe script de migracao para o schema atual?
- [ ] A migracao foi testada em um banco de staging (nao direto em producao)?
- [ ] Ha backup do banco de producao antes de aplicar a migracao?
- [ ] Se o projeto usa ORM (Prisma, TypeORM), o `schema.prisma` esta sincronizado com o banco?

### Bloco 5 — Testes Pre-Deploy
- [ ] Os testes automatizados passam com as variaveis de ambiente de staging?
- [ ] O Happy Path foi validado manualmente no ambiente de staging antes do deploy final?
- [ ] Existe um smoke test pos-deploy (acesso a URL, login basico, operacao critica)?

---

## O Processo de Deploy (Sequencia Obrigatoria)

### Passo 1: Preparacao (Fazer ANTES de qualquer push)
1. Rodar `git status` e confirmar que nenhum arquivo sensivel esta sendo commitado
2. Confirmar que o `.env.example` esta atualizado com todas as variaveis novas
3. Executar o Bloco 1 e Bloco 2 do checklist acima
4. Executar build local: `npm run build` (ou equivalente) e confirmar que nao ha erros
5. Rodar testes: `npm test` (ou equivalente) e confirmar 100% de aprovacao

### Passo 2: Staging (Obrigatorio antes de Producao)
1. Fazer push para a branch de staging ou abrir PR para a branch de staging
2. Aguardar build automatico no servidor de staging
3. Executar o Happy Path completo no ambiente de staging
4. Se houver migracao de banco: executar em staging primeiro e validar
5. Registrar o resultado da validacao (print ou log)

### Passo 3: Producao (Somente apos Staging aprovado)
1. Confirmar que todas as variaveis de ambiente de producao estao corretas no painel
2. Executar o merge ou push para a branch de producao
3. Aguardar build. Monitorar logs em tempo real durante os primeiros 5 minutos
4. Executar smoke test: acessar URL, fazer login, executar operacao mais critica
5. Se houver erro critico: executar rollback imediatamente (ver Plano de Rollback abaixo)

---

## Plano de Rollback

O plano de rollback deve ser definido ANTES do deploy, nao depois que o sistema quebrou.

### Rollback via Git (mais comum)
```
git log --oneline -5          # identificar o commit estavel anterior
git revert HEAD               # reverter o ultimo commit
git push origin main          # publicar a reversao
```

### Rollback via Painel do Servidor
Vercel, Railway e Heroku tem botao de "Redeploy" de versoes anteriores no painel.
Documentar onde fica esse botao no inicio do projeto, nao no momento da crise.

### Rollback de Banco de Dados
Se houve migracao: ter o script de down migration pronto e testado antes do deploy.
Nunca executar uma migracao que nao tenha script de reversao.

---

## Pos-Deploy: Monitoramento

- Monitorar logs de erro nas primeiras 2 horas apos deploy em producao
- Verificar se metricas de performance nao regrediram (tempo de resposta, uso de memoria)
- Confirmar com um usuario real que as funcionalidades criticas estao operando
- Registrar a data/hora do deploy bem-sucedido no CHANGELOG ou no historico de releases

---

## Lista de Verificacao Rapida para Deploy Solos

Para times de um dev, use esta lista condensada como checklist minimo nao-negociavel:

1. `.env.example` atualizado? Sim / Nao
2. Variaveis no servidor de producao conferidas? Sim / Nao
3. Nenhum "localhost" hardcoded? Sim / Nao
4. Build rodou sem erros? Sim / Nao
5. Staging validado? Sim / Nao
6. Rollback planejado? Sim / Nao

Se qualquer item for "Nao": nao fazer deploy. Resolver primeiro.

---

## Erros Comuns (O Que Este Guia Previne)

- "Funcionou na minha maquina" — O guia forca a validacao em staging antes de producao
- "Esqueci de adicionar a variavel no Vercel" — O Bloco 1 exige comparacao linha a linha
- "O banco travou depois da migracao" — O guia proibe migracao sem script de reversao testado
- "Nao tem como voltar atras rapido" — O Plano de Rollback e definido antes do deploy
- "Deployei na sexta a noite e o sistema caiu no final de semana" — Politica implicita:
  deploys criticos nao devem ser feitos em vesperas de feriados ou finais de semana
  sem cobertura de monitoramento
