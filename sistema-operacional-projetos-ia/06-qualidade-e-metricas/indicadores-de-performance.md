# 📊 INDICADORES DE PERFORMANCE DO PROJETO (KPIs) (SOP-IA)

## 1. O que é
A forma matemática de medir a saúde operacional do time e do projeto (diferente das *Métricas de Sucesso*, que medem o sucesso do negócio). Os Indicadores medem a velocidade e a fricção no desenvolvimento de Software Humano-IA.

## 2. Por que existe
Projetos parecem "estar fluindo muito bem" na cabeça do Engenheiro porque ele codou bastante, até descobrirmos que 40% foram retrabalhos ou "bugs". Os KPIs dão uma nota real, cortando o "achismo".

## 3. Quando usar
Analise-o na Reunião Retrospectiva do Fim da Sprint ou da Milestone Macra (Entre as Fases 03 e 05).

## 4. Como usar passo a passo
Fixe a meta dos indicadores no `plano-de-sprints.md`.
Use o Trello, GitHub ou JIRA para extrair.

## 5. Template Preenchível e Exemplos

```markdown
# Indicadores Operacionais 

### 1. Velocity (Velocidade)
- **O que é:** Quantos Pontos / Tarefas do Escopo fechamos por Sprint.
- **Bom:** Estabilidade (Entregou 10 na Sprint 1, 11 na Sprint 2). 
- **Ruim:** Alta variação (Entregou 20 e depois 2) indica dependências mal resolvidas na Fase 1 ou IAs codando lixo que precisa ser arrumado.

### 2. Taxa de Bugs Pós-Entrega (Escaped Defects)
- **O que é:** Quantos Bugs críticos as automações de Qa/UI deixaram vazar mesmo com o QA/PR Aprovado?
- **Bom:** Zero ou próximo. Significa que os Critérios de Aceite escritos em Marckdown no `02/criterios-de-aceite-template.md` foram eficientes e forçaram a IA a testar perfeitamente.
- **Ruim:** Altíssimo. A Definição de Pronto (`DoD`) do SOP-IA está sendo sistematicamente ignorada.

### 3. Lead Time to Value (Ciclo de Fechamento de Change Request)
- **O que é:** Se um Sponsor pediu mudança e assinou a `CR` hoje, quanto tempo levou até o cliente encostar na funcionalidade nova?

### 4. IA Assistance Rate (Taxa Opcional)
- **O que é:** Proporção do código base em arquivos *core* originados puramente por Automação vs Intervenção Humana bruta (Debugging na Madrugada). Se Humanos estão debuggando 60% do código à noite, o *Prompt Master* não impôs restrições claras e o Agente de IA "Hallsucinou" lógicas espaguetes num monolito frágil.
```

## 6. Exemplos Reais
Ao decorrer da automação no aplicativo base `Rayo SPED`, o "Lead Time" para fazer a IA entender as variáveis brutas do projeto sem o *SOP-IA* era gigantesco, levando-a a reescrever o Parse três vezes erradas (`Escaped Defects` altos). Uma vez injetado a obrigatoriedade de "ler a arquitetura (`Fase 04`) primeiro antes de gerar arquivos novos", o Bug-rate da IA caiu para próximo de Zero.

## 7. Métricas Associadas
- **Eficiência Técnica Relativa:** Qualidade Sustentada à Fricção Operacional Diária Baixa.
