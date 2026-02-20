# MODO STARTUP — GUIA DE OPERACAO PARA TIMES PEQUENOS (SOP-IA v2.0)

## O que e
A versao reduzida e pragmatica do SOP-IA para times de 1 a 3 pessoas, operando sob
restricao de tempo e sem camadas de governanca formal. Preserva os elementos
inegociaveis do framework (objetivo claro, criterios de aceite, deploy seguro) e
elimina o overhead de artefatos relevantes apenas para multi-squads.

## Nivel de Maturidade Minimo: 1
## Perfil Alvo: Dev solo, dupla ou trio em projetos de ate 6 semanas

---

## Principio do Modo Startup
Menos artefatos, mais disciplina nos artefatos que importam.
Um time pequeno quebra por falta de clareza, nao por falta de processo.
Tres documentos bem preenchidos valem mais que doze preenchidos pela metade.

---

## Os 3 Artefatos Inegociaveis (Minimo Absoluto)

### 1. objective.md
Um paragrafo. A dor. A solucao. O que nao e.
Sem isso: nao comece.

### 2. scope.md
Tres listas:
- O que o sistema FAZ (In-Scope)
- O que o sistema NAO FAZ (Out-of-Scope)
- O que o sistema pode fazer no futuro (Backlog Futuro)
Sem isso: a IA vai inventar features nao solicitadas.

### 3. deploy.md (ou o guia-de-deploy.md deste repositorio)
O checklist de variaveis de ambiente e validacao de staging pre-deploy.
Sem isso: o sistema vai quebrar em producao.

---

## Fluxo Simplificado para Projetos Solos

```
Semana 1:
  - Escrever objective.md (30 min)
  - Escrever scope.md (1h)
  - Setup do repositorio com .env.example e .gitignore
  - Injetar prompt-inicial-para-ia.md no agente

Semana 2-N (cada Sprint de 5 dias):
  - Segunda: revisar task.md, definir 3 a 5 tarefas da semana com criterio de aceite
  - Quarta: checkpoint: tarefas on track? Algum bloqueio?
  - Sexta: validar em staging. Nao mergeou pra main sem staging aprovado.

Ultimo dia do projeto:
  - Executar guia-de-deploy.md
  - Escrever acceptance-criteria.md final (o que foi entregue vs o que foi prometido)
  - Registrar aprendizados em benchmarks.md para o proximo projeto
```

---

## O Que Pode ser Ignorado no Modo Startup

| Artefato | Dispensavel? | Condicao |
|---|:---:|---|
| raci.md | Sim | Projetos solos |
| protocolo-de-escalacao.md | Sim | A menos que haja um sponsor externo |
| benchmarks-historicos.md | Opcional | Recomendado apos o 2o projeto |
| matriz-de-rastreabilidade.md | Opcional | Obrigatorio apenas em projetos criticos |
| audit.md | Sim | Ate o Nivel 3 de maturidade |
| limites-da-ia.md | Nao — Nunca dispensavel | Mesmo solos precisam definir o perimetro da IA |

---

## Regras Anti-Simplificacao Excessiva

O Modo Startup permite reduzir processo, mas nao permite:
1. Codar sem objetivo escrito
2. Fazer deploy sem checklist de variaveis de ambiente
3. Deixar a IA executar sem prompt estruturado
4. Declarar qualquer feature "pronta" sem o usuario real ter testado

---

## Sinal de Que Voce Precisa Sair do Modo Startup

- O projeto tem mais de 3 devs ativos
- O projeto tem usuarios reais com SLA de disponibilidade
- O projeto processa dados sensiveis (financeiro, saude, juridico)
- O ciclo de deploy e mais de 1 por semana em producao

Se qualquer item acima for verdadeiro: adote o `modo-enterprise.md`.
