# 🧠 EXEMPLO APLICADO: PROJETO SPED-PIS-COFINS (SOP-IA)

## 1. O que é
Um estudo de caso mestre (Case Study) demonstrando como um projeto real foi salvo por esta metodologia, indo de uma dor vaga do cliente para uma entrega técnica perfeita.

## 2. Por que existe
Para treinar novos Engenheiros e novos Agentes de IA. Quando alguém perguntar "Como preencho a Métrica de Sucesso?", deve ler este arquivo.

## 3. A Aplicação Real (Fase a Fase)

### Fase 01: O Início
- **A Dor Real (Kickoff):** "O Validador Oficial da Receita é ruim. Eu perco 3 dias abrindo TXTs gigantes para mudar alíquotas de PIS que vieram erradas do Supermercado."
- **Objetivo Definido (SOP):** Reduzir 3 dias de auditoria manual de impostos para 3 cliques no navegador, rodando 100% offline.
- **Prompt Master da IA:** Foi ordenado à IA que aturasse como Engenheiro de Performance. A IA foi proibida de usar Redux ou Contexts exaustivos que matassem a memória da Tab do Chrome.

### Fase 02: Definição Estratégica
- **Métricas Fechadas:** 
  - *Prazo:* 2 semanas.
  - *Risco:* Zero Arquivos Fiscais transitando em rede externa (Backend AWS vetado).
- **Escopo Base (In-Scope):** Fazer parse das Linhas C170, C191, C195.
- **Escopo Blindado (Out-of-Scope):** Não faremos login. Não faremos integração com APIs de contabilidade. (Essa blindagem economizou 1 mês de dev).
- **Ice Score (Priorização):** O Engine matemático de Grouping de NCM ganhou nota máxima absoluta, jogando a interface bonita e "tema dark" para a semana final.

### Fase 03 e 04: Planejamento e Arquitetura
- **A Grande Decisão (ADR #001):** Rejeitar Bancos de Dados completos e criar um *Virtual DOM Renderer* (`react-virtuoso`).
- A IA assumiu a geração da carcaça do Vite usando os padrões do `04/padroes-de-codigo.md`. Tudo ficou restrito na estrutura `/src/core` (Vanilla JS puro e testável) vs `/src/ui` (React Components visuais).

### Fase 05 e 06: Execução, O Bug e a Qualidade
- Durante a Sprint 2, surgiu um **Change Request (CR)**. O usuário relatou que os Registros `C191` do Fiscal agrupavam tudo numa única pasta `CNPJ` porque não possuíam NCM.
- Pelo SOP-IA, a IA não "criou telas novas" apavorada. Ela escreveu um Teste Unitário (`debug.mjs`) estritamente sobre aquela falha de cálculo.
- Descobriu-se que o NCM estava na linha "Pai" (`C190`).
- A IA aplicou o Conserto Matemático apenas na sub-root.
- O `Definion of Done (DoD)` impediu que a Modal "De-Para" subisse como "Concluída" sem as validações visuais completas (`plano-de-validacao.md`). Tudo foi retestado com TXTs de 100 mil itens. O App engoliu sem pestanejar.

---
**Conclusão do Case:** O método não só guiou a IA para gerar o código certo. O SOP-IA **impediu** a IA de gerar código que o usuário não precisava, no lugar errado, na arquitetura errada. 
O SOP-IA forçou a Excelência Extrema limitando a criatividade apenas à Solução Física.
