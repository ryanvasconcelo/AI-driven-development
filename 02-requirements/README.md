# requirements

**Fase de Definicao Estrategica**

Aqui o "o que fazer" e fechado em contrato. Tudo que nao esta nesta pasta nao existe
como requisito do projeto.

## Para que serve
Transforma o objetivo do Discovery em requisitos concretos, testáveis e priorizados.
Define as fronteiras do sistema (o que faz e o que nao faz), as metricas que definem
sucesso e os riscos conhecidos.

## Quando executar
Logo apos o Discovery ser aprovado. Antes de qualquer decisao de arquitetura.

## Beneficios
- Criterios de aceite escritos antes do codigo eliminam o retrabalho de "nao era isso que eu quis dizer"
- O out-of-scope formalmente documentado blinda o time de pedidos de ultima hora
- Os limites da IA definem o perimetro de autonomia do agente antes que ele cause estragos
- A matriz de priorizacao garante que os 20% do esforco que entregam 80% do valor sejam feitos primeiro

## Sequencia de Execucao
1. `scope.md` — In-Scope, Out-of-Scope e Backlog Futuro
2. `acceptance-criteria.md` — Criterio testavel para cada feature
3. `metrics.md` — 5 metricas com baseline e meta
4. `risks.md` — Riscos com mitigacao e contingencia
5. `prioritization.md` — ICE Score para o backlog
6. `ai-boundaries.md` — Niveis de autonomia do agente
7. `traceability.md` — Cadeia Objetivo -> Feature -> Criterio -> Evidencia

## Criterio para Avancar
O Sponsor assina o `scope.md`. Todo item do In-Scope tem pelo menos um criterio de aceite.
