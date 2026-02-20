# 📓 DECISION LOG TEMPLATE (ADR) (SOP-IA)

## 1. O que é
ADR (Architecture Decision Record). Um log imutável de "Por que diabos fizemos isso?". Registra escolhas arquiteturais, ferramentas ou padrões adotados, junto com o contexto da época.

## 2. Por que existe
A memória da equipe falha. Seis meses depois de adotar uma lib esotérica, ninguém lembra o motivo. O próximo Dev ou Agente IA fatalmente dirá: "Isso está horrível, vou refatorar". O ADR blinda as decisões do passado, fornecendo o "porquê" para análises futuras. A IA é instruída a ler o log antes de refatorar grandes partes do código.

## 3. Quando usar
Sempre que o arquiteto/dev/IA tomar uma decisão significativa que impacta a estrutura do projeto. Mudanças de frameworks, adoção de novas APIs ou DBs, ou cortes drásticos. Duração ideal: Não mais que 1 página por decisão.

## 4. Como usar passo a passo
1. Abra um arquivo incremental `ADR-001-nome-decisao.md` dentro de `docs/adrs/`.
2. Preencha o template abaixo registrando o Contexto, a Decisão em si e as Consequências.

## 5. Template Preenchível e Exemplos

```markdown
# ADR-001: Escolha do React-Virtuoso para Tabela UI

## 1. Status
✅ Aceito [DD/MM/AAAA]

## 2. Contexto
A Fase 03 exigiu renderizar dezenas de milhares de divs simultaneamente no `NcmGroupCard` de acordo com arquivos SPED de Varejistas (80MB). O DOM padrão do React congela e trava a Tab do Chrome ao renderizar mais de 3.000 nós de uma vez. A Métrica de Impacto era "Aumentar a velocidade", mas a aplicação esbarrou na arquitetura monothread do JS.

## 3. Decisão
Adotamos a virtualização da DOM utilizando a biblioteca `react-virtuoso`. Em vez de pré-renderizar todos os filhos do objeto NCM no CSS, a DOM recicla em Viewport apenas as divs imediatamente expostas na tela do usuário.

## 4. Consequências
- **Positivas:** Reduziu a carga RAM de 1.2GB para 90MB. O scroll atingiu taxa lisa de 60fps constantes até no limite de nós testados (40.000 divs).
- **Negativas/Trade-offs:** A Busca NATIVA do Navegador (Ctrl+F) parou de funcionar na tabela inteira, operando apenas nos itens já visíveis pela lib. Obrigando a criação de uma `Search Bar` nativa (via React State) como compensação no Layout.
```

## 6. Exemplos Reais
O conteúdo do ADR 001 listado no template acima foi a decisão real que destravou o projeto base deste framework.

## 7. Métricas Associadas
- **Nenhuma técnica.** Trata-se de registro cultural/histórico qualitativo.

## 8. Perguntas de Validação
- Se um Sênior assumir amanhã e perguntar "Por que não usamos a lib Y?". A resposta está claramente registrada aqui?

## 9. Checklist de Conformidade
- [ ] A IA foi ensinada nas "Regras de Engajamento" a gerar e preencher ADRs autonomamente sempre que pedir para adicionar pacotes grandes (`npm install x`) ou mudar paradigmas (ex: `Context` -> `Zustand`)?

## 10. Erros Comuns
- Tentar documentar "Decidi colocar botão azul". Isso fica no Figma/Fase Visual. ADR é pra decisões Sistêmico/Escalonáveis (Engenharia de Software).
