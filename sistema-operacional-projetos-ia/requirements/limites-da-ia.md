# LIMITES DA IA — PERIMETRO DE AUTONOMIA DO AGENTE (SOP-IA v2.0)

## O que e
Este documento define formalmente o que o agente de IA pode fazer de forma autonoma,
o que exige confirmacao humana e o que esta terminantemente proibido, independente
das instrucoes recebidas. Funciona como um contrato operacional entre o time humano
e o agente de IA.

## Por que existe
Agentes de IA com ferramentas de execucao real (edicao de arquivos, chamadas de API,
execucao de comandos no terminal) podem causar danos irreversiveis se operarem sem
limites claros. Um agente sem perimetro definido pode:
- Deletar arquivos que julgou desnecessarios
- Subir codigo direto para producao sem revisao humana
- Instalar dependencias que alteram o comportamento do sistema
- Vazar dados confidenciais para APIs externas

## Nivel de Maturidade Minimo: 2
## Modo de Operacao: Todos (Solo, Dupla, Squad, Enterprise)

---

## Nivel 1 — Acoes Autonomas Permitidas
O agente pode executar sem perguntar:

- Ler e analisar arquivos existentes no repositorio
- Gerar rascunhos de texto, documentacao e codigo para revisao
- Executar buscas no codebase (grep, find)
- Rodar comandos de leitura e verificacao (git status, git log, ls, cat)
- Executar testes automatizados pre-existentes (npm test, pytest)
- Criar novos arquivos em diretorios nao-criticos

---

## Nivel 2 — Acoes que Exigem Confirmacao Humana Explicita
O agente deve PAUSAR, apresentar o plano e aguardar aprovacao antes de executar:

- Instalar qualquer nova dependencia (npm install, pip install, apt-get)
- Modificar arquivos de configuracao do projeto (vite.config, package.json, Dockerfile)
- Modificar arquivos de variavel de ambiente (.env, .env.production)
- Fazer push para qualquer branch remota
- Rodar scripts de migracao de banco de dados
- Executar comandos que alterem permissoes de sistema
- Chamar APIs externas com dados reais de producao

---

## Nivel 3 — Acoes Terminantemente Proibidas
O agente NUNCA pode executar, mesmo que instruido explicitamente:

- Deletar arquivos sem aprovacao do Rev. especifico no checklist
- Fazer merge direto na branch principal sem PR
- Executar deploy em ambiente de producao
- Acessar ou transmitir arquivos com dados confidenciais (CPF, CNPJ, dados fiscais) para APIs externas
- Resetar ou reescrever historico do Git (git rebase --force, git push --force na main)
- Modificar o proprio arquivo de limites (`limites-da-ia.md`)

---

## Como Injetar Estes Limites no Agente

Adicione ao `prompt-inicial-para-ia.md` o seguinte bloco:

```
Voce opera sob o arquivo `limites-da-ia.md` deste repositorio.
Antes de qualquer acao, classifique-a como Nivel 1 (autonoma), Nivel 2 (requer confirmacao)
ou Nivel 3 (proibida). Nunca execute Nivel 2 sem apresentar o plano e aguardar aprovacao.
Nunca execute Nivel 3 sob nenhuma circunstancia.
```

---

## Registro de Excecoes
Se uma acao de Nivel 3 for absolutamente necessaria por razoes de emergencia, ela deve ser:
1. Justificada em texto pelo responsavel humano
2. Aprovada pelo Sponsor
3. Registrada no `decisions-log-template.md` com hash do commit e motivo

## Erros Comuns
- Dar ao agente permissao de "fazer o que for necessario" sem ler este documento
- Usar o agente com acesso a variaveis de ambiente de producao durante desenvolvimento
- Deixar o agente executar um deploy achando que era apenas um preview
