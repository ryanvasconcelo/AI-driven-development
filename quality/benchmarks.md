# BENCHMARKS E HISTORICO DE PROJETOS (SOP-IA v2.0)

## O que e
O registro comparativo entre projetos ao longo do tempo. Funciona como memoria
organizacional quantificada: elimina o "achismo" sobre quanto tempo as coisas levam
e fornece baseline real para estimar projetos futuros.

## Nivel de Maturidade Minimo: 3
## Modo de Operacao: Recomendado para todos a partir do segundo projeto

---

## Template de Registro por Projeto

```markdown
## Projeto: [Nome]
- Data de inicio: [DD/MM/AAAA]
- Data de entrega: [DD/MM/AAAA]
- Duracao planejada: [X semanas]
- Duracao real: [X semanas]
- Variancia de prazo: [+X% ou -X%]

### Time
- Modo de operacao: [Solo / Dupla / Squad]
- Principal agente de IA usado: [Nome e versao]
- Proporcao estimada de codigo gerado por IA: [XX%]

### Metricas de Qualidade
- Bugs criticos em producao no primeiro mes: [N]
- Causas de bugs de deploy (variaveis, links, schema): [Listar]
- Change Requests abertos durante o projeto: [N]
- Change Requests aprovados: [N]

### Metricas de Impacto
- Metrica de impacto prometida: [Ex: reduzir de 3 dias para 3 cliques]
- Metrica de impacto realizada: [Ex: reducao confirmada pelo usuario em 3 semanas de uso]

### Licoes Aprendidas
- O que aceleraria o proximo projeto similar?
- Qual artefato do SOP-IA foi mais util?
- Qual artefato do SOP-IA foi overhead real (nao foi usado)?
```

---

## Exemplo Aplicado (SPED-PIS-COFINS)

```markdown
## Projeto: Automacao SPED PIS-COFINS (Rayo v1.0)
- Data de inicio: 2025-02-19
- Data de entrega: 2025-02-20
- Duracao planejada: 2 dias (sprint intensiva)
- Duracao real: 2 dias
- Variancia de prazo: 0%

### Time
- Modo de operacao: Solo (1 Dev + IA)
- Agente: Antigravity (Gemini-based)
- Proporcao de codigo por IA: ~75%

### Metricas de Qualidade
- Bugs criticos em producao: 0 (processamento 100% client-side, sem deploy de producao)
- Change Requests: 3 (De-Para engine, agrupamento C191, virtualizacao DOM)
- Change Requests aprovados: 3

### Metricas de Impacto
- Prometida: auditoria de 3 dias -> 3 cliques
- Realizada: confirmado em sessao de validacao com arquivos reais de 55MB

### Licoes Aprendidas
- O `guia-de-deploy.md` teria evitado confusao com a estrutura do Git no repositorio pai
- O `modelo-de-maturidade.md` teria acelerado a definicao da stack desde o dia 1
- O `task.md` foi o artefato mais usado e mais util do projeto inteiro
```

---

## Analise Comparativa (A partir do 3o Projeto)

| Indicador | Projeto 1 | Projeto 2 | Projeto 3 | Tendencia |
|---|:---:|:---:|:---:|:---:|
| Variancia de prazo (%) | — | — | — | — |
| Bugs em producao | — | — | — | — |
| CRs abertos | — | — | — | — |
| Lead time medio (dias) | — | — | — | — |

Preencha esta tabela ao final de cada projeto. Apos 3 projetos, a tendencia revela
o impacto real do SOP-IA na maturidade de entrega da equipe.
