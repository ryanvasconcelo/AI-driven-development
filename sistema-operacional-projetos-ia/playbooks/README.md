# playbooks

**Modos de Operacao**

Como calibrar o SOP-IA para o seu contexto. Um dev solo nao precisa do mesmo processo
que um squad de oito pessoas com SLA.

## Para que serve
Definir quais artefatos sao obrigatorios, quais sao opcionais e quais sao overhead
real dependendo do tamanho do time e da criticidade do projeto.

## Arquivos
- `startup-mode.md` — Para times de 1 a 3 devs. Tres artefatos minimos inegociaveis.
  Fluxo condensado para projetos de ate 6 semanas.
- `enterprise-mode.md` — Para squads de 3+. Todos os artefatos obrigatorios.
  Governance multi-dev, RACI formal, rastreabilidade completa.

## Como Escolher
Se voce e dev solo ou dupla em um projeto sem SLA: comece pelo `startup-mode.md`.
Se voce tem squad estruturado, dados sensiveis ou usuarios reais dependentes: `enterprise-mode.md`.

## Regra de Transicao
O projeto nao precisa comecar em Enterprise para evoluir para la.
Comece pelo Startup e evolua quando os sinais de transicao forem atingidos
(detalhados em cada arquivo).
