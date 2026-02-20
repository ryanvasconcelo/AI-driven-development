# SOP-IA — Sistema Operacional de Projetos Orientado por IA

> Um framework de governança para times que usam IA no desenvolvimento de software e precisam de previsibilidade, qualidade e rastreabilidade — não de sorte.

---

## O Problema que Este Framework Resolve

A maioria dos times que usa IA no desenvolvimento enfrenta o mesmo paradoxo: a IA acelera a escrita de código, mas não acelera a entrega de valor. O motivo é que o gargalo nunca foi a velocidade de digitação — foi a ausência de método.

Sem escopo fechado, a IA expande o problema.
Sem critérios de aceite, a IA entrega o que interpretou, não o que foi pedido.
Sem governança, a IA adiciona complexidade onde deveria adicionar clareza.

O SOP-IA resolve isso transformando a IA de gerador de código em copiloto de governança.

---

## O que o SOP-IA Entrega

| Antes | Depois |
|---|---|
| Escopo implícito, acordado verbalmente | Escopo fechado em contrato, aprovado pelo Sponsor |
| "Está pronto" sem evidência | Definition of Done com critério verificável |
| Deploy manual com suor frio | Checklist de release com rollback planejado |
| IA gerando código sem contexto | IA operando com prompt mestre e limites definidos |
| Projeto dependente de memória individual | Projeto documentado, auditável, replicável |
| Prazo como estimativa otimista | Roadmap com variância controlada e histórico comparativo |

---

## Prova de Conceito

O framework foi extraído e generalizado a partir de um projeto real:

**Projeto:** Automação de auditoria fiscal SPED PIS/COFINS
**Estimativa original:** ~1 semana
**Entrega com SOP-IA:** ~3 horas
**O que mudou:** Não foi a velocidade da IA. Foi o método aplicado antes de acionar a IA.

Estudo de caso completo disponível em [`case-studies/sped-pis-cofins.md`](./case-studies/exemplo-aplicado-sped.md).

---

## Estrutura do Framework

```
sistema-operacional-projetos-ia/
│
├── getting-started/          ← Comece aqui. Visão geral e modelo de maturidade.
│
├── discovery/                ← Fase 1: Kickoff, objetivo, acessos, prompt da IA.
├── requirements/             ← Fase 2: Escopo, critérios de aceite, métricas, riscos.
├── planning/                 ← Fase 3: Roadmap, sprints, testes, validação.
├── architecture/             ← Fase 4: Stack, estrutura de pastas, padrões, ADRs.
├── execution/                ← Fase 5: Checklists diário, pré-merge, release, deploy.
├── quality/                  ← Fase 6: Definition of Done, KPIs, auditoria, benchmarks.
│
├── guardrails/               ← As 6 Leis Anti-Desvio e o Contrato de Compromisso.
├── playbooks/                ← Modo Startup (1–3 devs) e Modo Enterprise (squads).
├── case-studies/             ← Exemplos reais com artefatos preenchidos.
│
├── glossario.md              ← Definições formais de todos os termos do framework.
├── CHANGELOG.md              ← Histórico de versões do framework.
├── ROADMAP.md                ← O que vem nas próximas versões.
└── CONTRIBUTING.md           ← Como contribuir e evoluir o framework.
```

---

## As 3 Leis do SOP-IA para Agentes de IA

```
1. Nunca gere código sem Critério de Aceite explícito.
2. Registre toda decisão arquitetural no ADR antes de implementar.
3. Recuse pedidos fora do escopo aprovado e acione o Change Request.
```

Estas leis são injetadas no agente via [`discovery/prompt-inicial-para-ia.md`](./discovery/prompt-inicial-para-ia.md) no início de cada projeto.

---

## Como Usar

### Opção 1 — Novo projeto
Clone este repositório e copie a pasta `sistema-operacional-projetos-ia/` para a raiz do seu projeto. Siga a sequência de fases começando por `getting-started/README.md`.

### Opção 2 — Projeto em andamento
Identifique em qual fase o projeto se encontra, preencha os artefatos retroativamente para as fases anteriores (mesmo que resumido), e aplique o framework a partir do ponto atual.

### Opção 3 — Calibrar pelo tamanho do time
- **Solo ou dupla:** Leia [`playbooks/startup-mode.md`](./playbooks/startup-mode.md) — 3 artefatos obrigatórios, fluxo condensado.
- **Squad de 3+ devs:** Leia [`playbooks/enterprise-mode.md`](./playbooks/enterprise-mode.md) — governança completa com RACI e rastreabilidade.

---

## Modelo de Maturidade

O SOP-IA define 5 níveis de maturidade operacional. Antes de adotar o framework completo, identifique onde o seu time está:

| Nível | Perfil | Foco Imediato |
|:---:|---|---|
| 1 | Reativo — sem documentação consistente | Escrever objetivo e escopo em todo projeto |
| 2 | Definido — documentação inconsistente | Adotar critérios de aceite e checklist pré-merge |
| **3** | **Gerenciado — alvo para a maioria dos times** | **100% dos projetos com Kickoff, DoD e deploy seguro** |
| 4 | Otimizado — métricas históricas orientam estimativas | Benchmarks comparativos entre projetos |
| 5 | Sistematizado — framework auto-sustentável | Onboarding via documentação, sem dependência de pessoas |

Avaliação completa em [`getting-started/modelo-de-maturidade.md`](./getting-started/modelo-de-maturidade.md).

---

## Métricas que o Framework Monitora

- **Variância de Prazo:** diferença entre entrega planejada e real, por projeto
- **Escaped Defects:** bugs críticos que chegaram a produção após aprovação de QA
- **Change Requests por Projeto:** indicador indireto da qualidade do Kickoff
- **Lead Time médio:** do backlog ao deploy, medido historicamente em `quality/benchmarks.md`
- **SOP Compliance Score:** % de artefatos preenchidos por projeto

---

## Versão Atual

**v2.0.0** — Enterprise-Grade
Adicionados: modelo de maturidade, RACI, limites da IA, matriz de rastreabilidade, guia de deploy anti-falha, protocolo de escalação, benchmarks históricos, modos de operação, glossário formal.

Histórico completo em [`CHANGELOG.md`](./CHANGELOG.md).

---

## Projeto de Referência

**[ryanvasconcelo/sped-pis-cofins](https://github.com/ryanvasconcelo/sped-pis-cofins)**
Aplicativo React/Vite local que automatiza auditoria e correção de alíquotas PIS/COFINS em arquivos SPED EFD-Contribuições, processando 80.000+ registros sem banco de dados externo. Desenvolvido integralmente sob o SOP-IA v1.0.
