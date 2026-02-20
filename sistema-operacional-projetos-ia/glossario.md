# GLOSSARIO — SOP-IA v2.0

Este documento define formalmente todos os termos utilizados no framework.
Qualquer membro do time humano ou agente de IA deve consultar este glossario antes
de questionar o significado de um termo durante o projeto.

---

## A

**Acceptance Criteria (Criterio de Aceite)**
Condicao verificavel, binaria (pass/fail) e escrita antes do inicio do desenvolvimento
de uma feature. Define com precisao o comportamento esperado do sistema sob um contexto
especifico. Nao pode conter termos subjetivos como "rapido" ou "bonito".

**ADR (Architecture Decision Record / Log de Decisao Arquitetural)**
Documento imutavel que registra uma decisao tecnica significativa: o contexto da epoca,
a opcao escolhida, as alternativas descartadas e as consequencias esperadas. Nao pode
ser deletado; apenas marcado como "Substituido por ADR-XXX".

**Agent (Agente de IA)**
Sistema de inteligencia artificial com capacidade de executar acoes autonomas
(ler arquivos, escrever codigo, rodar testes, chamar APIs) sem intervencao humana em
cada passo. Diferente de um chatbot, um agente persiste contexto e executa sequencias
longas de tarefas. Deve operar dentro dos limites definidos em `limites-da-ia.md`.

---

## B

**Backlog**
Lista priorizada de todas as tarefas e features planejadas para o projeto. O topo do
backlog representa o trabalho com maior ICE Score (maior impacto e menor risco).

**Baseline**
O valor atual de uma metrica antes do inicio de uma iniciativa de melhoria.
Sem baseline, nao e possivel medir o impacto real de nenhuma mudanca.

---

## C

**Change Request (CR / Controle de Mudanca)**
Processo formal acionado quando uma solicitacao de trabalho nao estava prevista no
escopo original aprovado. Nenhuma mudanca de escopo pode ser implementada sem
um CR aprovado pelo Sponsor.

**Code Freeze**
Estado do repositorio onde nenhum novo codigo pode ser mergeado na branch principal.
Ativado antes de uma Release para garantir estabilidade total do build.

**Critério de Aceite**
Ver "Acceptance Criteria".

---

## D

**Definition of Done (Definicao de Pronto / DoD)**
Lista universal de criterios que QUALQUER feature deve cumprir para ser declarada
concluida. E diferente do Criterio de Aceite, que e especifico de cada feature.
A DoD e universal para o projeto inteiro.

**Deploy**
Ato de publicar o codigo versionado de um ambiente de desenvolvimento para um
ambiente acessivel ao usuario final (Staging ou Producao).

---

## E

**Epic (Epico)**
Conjunto de features ou tarefas de mesmo dominio logico que juntas entregam um
valor de negocio identificavel. Um Epic pode durar varias Sprints.

---

## F

**Feature**
Funcionalidade especifica do sistema que resolve uma necessidade do usuario. Toda
feature deve ter pelo menos um Criterio de Aceite associado antes de ser iniciada.

---

## I

**ICE Score**
Metodo de priorizacao baseado em tres dimensoes: Impact (Impacto), Confidence
(Confianca) e Ease (Facilidade). Score = (Impact x Confidence x Ease) / 100.
Quanto maior o score, maior a prioridade.

---

## L

**Lead Time**
Tempo total decorrido desde a criacao de uma tarefa no backlog ate a entrega dessa
tarefa em producao para o usuario final.

---

## M

**Milestone**
Marco de entrega de alto nivel que representa a conclusao de um conjunto de Epicos
ou Sprints. E o granulo minimo de entrega validavel pelo Sponsor.

**MVP (Minimum Viable Product)**
Versao minima de um produto que entrega o valor central prometido e permite validacao
real com usuarios sem features adicionais. Nao e um produto ruim; e deliberadamente
focado.

---

## O

**Out-of-Scope**
Toda e qualquer funcionalidade, tecnologia ou requisito que foi formalmente declarado
fora dos limites do projeto atual. Implementar algo Out-of-Scope sem um CR aprovado e
uma violacao direta do SOP-IA.

---

## P

**PR (Pull Request)**
Pedido formal de incorporacao de codigo de uma branch de trabalho para a branch
principal do repositorio. Todo PR deve passar pelo Checklist Pre-Merge antes de
ser aprovado.

---

## R

**RACI**
Matriz que define quatro papeis por atividade: Responsavel (quem executa), Aprovador
(quem da o aceite final), Consultado (quem e ouvido), Informado (quem precisa saber).
Resolve ambiguidades de ownership em projetos com mais de uma pessoa.

**Rollback**
Procedimento de reverter o sistema para um estado estavel anterior quando um deploy
causa falhas criticas. Deve ser documentado e testavel antes de qualquer release.

---

## S

**SLA (Service Level Agreement)**
Acordo formal que define metricas minimas de disponibilidade, tempo de resposta ou
qualidade esperadas de um servico. Relevante em projetos com usarios reais e expectativas
de uptime.

**SOP-IA**
Sistema Operacional de Projetos Orientado por IA. Este framework.

**Sponsor**
A pessoa ou papel com autoridade final para aprovar escopo, mudancas e entregas.
Geralmente e o cliente, o CEO, ou o diretor responsavel pelo projeto.

**Sprint**
Ciclo curto e fixo de trabalho (tipicamente 1 a 2 semanas) com objetivo e backlog
definidos no inicio. Ao final de uma Sprint, deve existir um incremento testavel e
demonstravel.

**Staging**
Ambiente tecnico identico ou proximo a Producao, usado para validar o sistema antes
da publicacao final para o usuario real.

---

## T

**Tech Debt (Divida Tecnica)**
Custo futuro decorrente de uma decisao tecnica deliberadamente subotima no presente.
Toda divida tecnica deve ser registrada no backlog como uma tarefa de pagamento.

**Truck Factor**
Numero de membros do time que, se ficassem indisponiveis ao mesmo tempo, travaria
o projeto por falta de conhecimento exclusivo. Times com Truck Factor = 1 estao em
risco critico.

---

## V

**Velocity (Velocidade)**
Quantidade media de pontos ou tarefas entregues por Sprint. Usada para estimar
capacidade futura do time.

**Versionamento Semantico**
Padrao de numeracao de versoes no formato MAJOR.MINOR.PATCH.
MAJOR: mudancas incompativeis. MINOR: funcionalidades novas retrocompativeis.
PATCH: correcoes de bugs.
