# 🚀 SISTEMA OPERACIONAL DE PROJETOS ORIENTADO POR IA

## 1. O que é
O Sistema Operacional de Projetos Orientado por IA (SOP-IA) é o *framework mestre* da organização. Ele atua como um trilho inflexível para a ideação, planejamento, execução e entrega de qualquer projeto (Software, Dados, RPA, Produto Digital). Ele parametriza como humanos e agentes de IA colaboram para garantir 100% de previsibilidade, qualidade técnica e ausência de desvios de escopo.

## 2. Por que existe
Projetos frequentemente falham ou excedem orçamentos devido a:
- **Escopos implícitos** (assunções não documentadas).
- **Falta de Critérios de Aceite** (o que significa "pronto"?).
- **Complexidade acidental** (engenharia excessiva sem necessidade de negócio).
- **Uso não-estruturado de IA** (onde a IA atua como um gerador de código desgovernado em vez de um co-piloto estratégico).

Este sistema elimina o caos, forçando a clareza extrema *antes* que a primeira linha de código seja escrita.

## 3. Quando usar
**Sempre.** Não há exceções. Desde um script de automação de 2 horas até uma plataforma core de 6 meses, todo repositório deve ser inicializado, governado e auditado pelos artefatos deste SOP.

## 4. Como usar (Passo a Passo)

A espinha dorsal deste sistema é baseada no modelo mental usado com sucesso no projeto base `SPED-PIS-COFINS`. Você deve seguir estritamente as fases abaixo:

### Fase 01: Início do Projeto (Discovery & Setup)
1. Responda ao `perguntas-obrigatorias.md` exaustivamente.
2. Defina o objetivo central em `definicao-de-objetivo.md`. Se não puder ser explicado em um tweet, está incorreto.
3. Obtenha todos os tokens, APIs e acessos em `levantamento-acessos.md`.
4. Preencha e aprove o `template-kickoff.md` com os stakeholders.
5. Inicialize a IA com o contexto usando o `prompt-inicial-para-ia.md`.

### Fase 02: Definição Estratégica (O "Contrato")
1. Escreva o `escopo-template.md`. Onde houver dúvida, documente o que está **fora do escopo**.
2. Defina os `criterios-de-aceite-template.md`. Se não for testável, não é um critério.
3. Preencha as `metricas-de-sucesso-template.md` (As 5 Métricas Obrigatórias).
4. Mapeie os `riscos-e-dependencias-template.md`.
5. Priorize implacavelmente usando a `matriz-de-priorizacao.md`.

### Fase 03: Planejamento Operacional (O Mapa)
1. Crie o `roadmap-template.md` macro.
2. Quebre o roadmap no `plano-de-sprints.md`.
3. Defina como a garantia de qualidade será feita com o `plano-de-testes.md` e o `plano-de-validacao.md`.

### Fase 04: Arquitetura e Organização (A Fundação Técnica)
1. Desenhe a `arquitetura-template.md`. Prefira simplicidade à "escalabilidade hipotética futura".
2. Estabeleça os `padroes-de-codigo.md`.
3. Crie o repositório base segundo a `estrutura-base-de-projeto.md`.
4. Qualquer mudança arquitetural deve gerar uma entrada no `decisions-log-template.md`.

### Fase 05: Execução e Governança (O Motor)
1. O desenvolvedor/IA deve iniciar o dia validando o `checklist-diario.md`.
2. O código só entra na branch principal se passar pelo `checklist-pre-merge.md`.
3. Mudanças de escopo descobertas no caminho devem passar pelo `controle-de-mudancas.md`.
4. Deploys são executados com o `checklist-release.md`.

### Fase 06: Qualidade e Métricas (A Auditoria)
1. Meça o impacto com os `indicadores-de-performance.md`.
2. A feature só existe se cumprir integralmente a `definicao-de-pronto.md`.
3. O C-Level ou Tech Lead audita a entrega final via `auditoria-de-projeto.md`.

## 5. Exemplos Reais
Consulte a pasta `07-exemplos-aplicados` para ver exatamente como os artefatos foram preenchidos para gerar o sucesso do `SPED-PIS-COFINS`.

## 6. Métricas Associadas
- **Adesão ao Framework:** % de projetos que possuem todos os artefatos preenchidos na raiz.
- **Variância de Escopo:** % de tarefas adicionadas vs. tarefas planejadas originalmente.
- **Defeitos Vasados:** Falhas encontradas em produção que deveriam ter sido pegas no `checklist-pre-merge.md`.

## 7. Perguntas de Validação
- O objetivo do projeto resolve uma dor de negócio quantificável?
- Os critérios de aceite impedem duplas interpretações?
- A IA foi devidamente "conteinerizada" como copiloto estruturado via prompt inicial?

## 8. Checklist de Conformidade
- [ ] O SOP-IA foi copiado para a raiz do novo repositório?
- [ ] O Kickoff foi assinado?
- [ ] A Definição de Pronto foi afixada?

## 9. Erros Comuns
- **"É um projeto pequeno, não precisamos do SOP":** É assim que projetos de fim de semana viram labirintos de 3 meses.
- **Microgerenciamento pela IA:** Ignorar a documentação e pedir código cegamente à IA.
- **Métricas de Vaidade:** Medir "linhas de código" ou "commits" em vez de valor de negócio entregue.
