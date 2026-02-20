# MODO ENTERPRISE — GUIA DE OPERACAO PARA TIMES MEDIOS E CRITICOS (SOP-IA v2.0)

## O que e
A versao completa do SOP-IA para projetos com mais de 3 devs ativos, usuarios reais com
SLA, dados sensiveis ou necessidade de auditoria formal. Inclui todas as camadas de
governanca, rastreabilidade e conformidade do framework.

## Nivel de Maturidade Minimo: 3
## Perfil Alvo: Squads de 3 a 10 devs, projetos criticos, sistemas com usuarios reais

---

## Diferenca Fundamental em Relacao ao Modo Startup

No Modo Startup, a disciplina substitui o processo. No Modo Enterprise, o processo
institucionaliza a disciplina. A diferenca nao e burocracia por burocracia, e
rastreabilidade que sobrevive a rotatividade de pessoas.

---

## Artefatos Obrigatorios no Modo Enterprise

### Fase de Discovery
- [ ] kickoff.md (assinado pelo Sponsor)
- [ ] objective.md (1 paragrafo aprovado pelo Sponsor)
- [ ] scope.md (In-Scope, Out-of-Scope, Backlog Futuro)
- [ ] raci.md (preenchido para cada fase do projeto)
- [ ] access-map.md (todos os acessos mapeados no dia 0)
- [ ] ai-prompt.md (prompt mestre do agente disponivel no repo)
- [ ] ai-boundaries.md (limites de autonomia da IA definidos)

### Fase de Requisitos
- [ ] acceptance-criteria.md (100% das features com criterio testavel)
- [ ] metrics.md (5 metricas com baseline e meta)
- [ ] risks.md (ao menos 3 riscos criticos com mitigacao)
- [ ] traceability.md (cadeia Objetivo -> Feature -> Criterio -> Evidencia)
- [ ] scope-contract.md (documento formal de fronteiras aprovado e assinado)

### Fase de Execucao
- [ ] daily-checklist.md em uso por todos os devs
- [ ] pre-merge.md bloqueando merges sem aprovacao
- [ ] change-request.md acionado para todo pedido out-of-scope
- [ ] adr.md atualizado a cada decisao arquitetural significativa
- [ ] escalation.md em uso para resolver impasses

### Fase de Qualidade
- [ ] definition-of-done.md fixado e revisado por todos
- [ ] audit.md preenchido antes de toda release maior
- [ ] kpis.md atualizado ao fim de cada sprint
- [ ] benchmarks.md atualizado ao fim do projeto

### Deploy
- [ ] deploy.md executado integralmente, incluindo staging
- [ ] release.md assinado antes de qualquer push para producao
- [ ] Plano de rollback documentado e testado

---

## Governanca Multi-Dev no Modo Enterprise

### Regras de Branch
- Nenhum dev (humano ou IA) faz push direto na branch `main`
- Todo codigo vai por PR com pelo menos 1 aprovacao humana
- Branches seguem nomenclatura padrao: `feature/nome`, `fix/nome`, `chore/nome`

### Responsabilidades Fixas por Role
- **Tech Lead:** Aprova arquitetura, ADRs e releases. Nao e aprovador de PR triviais.
- **Dev:** Executa, testa, documenta. Abre CR quando necessario.
- **Agente IA:** Executa dentro dos limites do `ai-boundaries.md`. Nunca aprova.
- **Sponsor:** Aprova escopo, mudancas de escopo e entrega final.

### Cadencia de Revisao
- Daily: `daily-checklist.md` por cada dev
- Semanal: Retrospectiva do Sprint + atualizacao do `kpis.md`
- Mensal: Revisao de maturidade + atualizacao dos `benchmarks.md`
- Por projeto: `audit.md` antes de cada release

---

## Sinal de Que o Modo Enterprise Esta Sendo Usado Errado

- O time gasta mais de 30% do tempo preenchendo documentos e menos de 70% em execucao
- Os artefatos sao preenchidos "para cumprir tabela" e nao sao lidos depois
- Nenhum artefato foi atualizado apos a aprovacao inicial

Se isso ocorrer: retornar ao `startup-mode.md` e identificar qual artefato e overhead
real vs qual e overhead percebido por falta de habito.
