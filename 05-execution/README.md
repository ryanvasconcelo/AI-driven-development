# execution

**Fase de Execucao e Governanca**

O dia a dia do projeto. Contem os checklists e protocolos que garantem que o que foi
planejado e o que e executado sejam a mesma coisa.

## Para que serve
Governa o fluxo diario de trabalho: o que verificar antes de comecar, o que verificar
antes de mergear, como fazer deploy sem quebrar producao, e o que fazer quando algo
da errado ou muda.

## Quando executar
Durante todo o ciclo de desenvolvimento. Esta pasta e usada todos os dias.

## Beneficios
- O `deploy.md` elimina o padrao de "funcionou aqui, quebrou em producao" com um checklist
  de variaveis de ambiente, URLs e staging obrigatorio antes de qualquer push para producao
- O `pre-merge.md` impede que codigo sem teste ou documentacao entre na branch principal
- O `change-request.md` registra formalmente pedidos de mudanca de escopo, evitando
  que o projeto cresça silenciosamente ate ficar incontrolavel
- O `escalation.md` define o que fazer quando a IA trava ou o Sponsor muda de ideia

## Arquivos e Uso
- `daily-checklist.md` — Executar no inicio de cada sessao de trabalho
- `pre-merge.md` — Executar antes de todo Pull Request
- `release.md` — Executar antes de toda release para producao
- `deploy.md` — O guia anti-falha de deploy (LEIA ANTES DO PRIMEIRO DEPLOY)
- `change-request.md` — Abrir sempre que o escopo for questionado
- `escalation.md` — Seguir quando houver impasse tecnico ou de escopo

## Criterio de Uso Correto
Se bugs de producao por variaveis de ambiente ou URLs erradas persistem: o `deploy.md`
nao esta sendo executado. Cobrar seu proprio cumprimento.
