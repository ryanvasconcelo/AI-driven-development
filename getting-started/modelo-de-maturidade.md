# MODELO DE MATURIDADE — SOP-IA v2.0

## O que e
O Modelo de Maturidade e um sistema de auto-avaliacao de cinco niveis que permite a
qualquer time ou empresa identificar em que ponto do espectro de maturidade em engenharia
orientada por IA eles se encontram. Cada nivel descreve comportamentos observaveis,
nao opinioes.

## Por que existe
Um framework sem escala de maturidade e como uma academia sem avaliacao fisica inicial:
todos recebem o mesmo treino, independente da condicao. O resultado e abandono precoce
por quem achou dificil demais e negligencia por quem achou facil demais.

## Como usar
1. Responda honestamente as perguntas diagnosticas de cada nivel.
2. O nivel mais alto em que voce responde "nao" a pelo menos um item e o seu nivel atual.
3. Use o plano de evolucao para subir ao proximo nivel antes de adotar o SOP-IA completo.

---

## Nivel 1 — Reativo
**Descricao:** O time opera sem documentacao consistente. Decisoes sao tomadas verbalmente
e perdidas. O deploy e manual e ad-hoc. A IA e usada como gerador de codigo sem governanca.

**Sinais Observaveis:**
- Nao existe um arquivo de escopo formalmente aprovado em nenhum projeto ativo
- O time nao sabe quais features estao "prontas" vs "em progresso" sem perguntar alguem
- Deploys de producao sao executados diretamente da maquina do dev sem ambiente de staging
- A IA e acionada com instrucoes vagas e o resultado e revisado manualmente

**Plano de Evolucao para Nivel 2:**
- Criar um `task.md` com marcadores de estado em cada projeto ativo
- Definir e escrever o objetivo de cada projeto em uma frase
- Usar o `prompt-inicial-para-ia.md` para estruturar o primeiro proximo projeto

---

## Nivel 2 — Definido
**Descricao:** O time tem documentacao basica de objetivos e escopo, mas ela e inconsistente
entre projetos. A IA e usada com alguma estrutura. Existe um repositorio organizado.
Deploys tem um roteiro, mas nao ha checklist formal.

**Sinais Observaveis:**
- Pelo menos 50% dos projetos ativos tem um arquivo de objetivo e escopo escrito
- A IA recebe um prompt estruturado antes de codar
- Existe um Criterio de Aceite para as features mais criticas
- Bugs de producao sao rastreados mas nao correlacionados a falhas de processo

**Plano de Evolucao para Nivel 3:**
- Adotar o `template-kickoff.md` em todos os novos projetos
- Implementar o `checklist-pre-merge.md` antes de todo merge na branch principal
- Escrever Criterios de Aceite para 100% das features antes de iniciar o desenvolvimento

---

## Nivel 3 — Gerenciado (NIVEL ALVO PARA ESTE TIME)
**Descricao:** O time usa o SOP-IA de forma consistente. Existe rastreabilidade entre
objetivo, feature e teste. A IA opera dentro de limites definidos. Deploys seguem um
checklist. Metricas sao coletadas e revisadas ao fim de cada projeto.

**Sinais Observaveis:**
- 100% dos projetos tem Kickoff, Escopo e Definition of Done documentados
- O agente de IA tem um prompt mestre e limites de autonomia claros
- O deploy segue o `guia-de-deploy.md` e erros de ambiente sao raros
- A equipe consegue auditar um projeto passado sem depender de memoria

**Indicadores de Nivel 3 Atingido:**
- Frequencia de bugs de producao causados por variaveis de ambiente: menor que 1 por trimestre
- Projetos entregues dentro de 10% do prazo estimado: maior que 70%
- Criterios de Aceite escritos antes do desenvolvimento: 100%

**Plano de Evolucao para Nivel 4:**
- Implementar benchmarks historicos entre projetos
- Adotar o protocolo RACI em projetos com mais de um dev ativo
- Criar registro de ADRs para todas as decisoes arquiteturais

---

## Nivel 4 — Otimizado
**Descricao:** O time usa metricas historicas para estimar projetos futuros. Os processos
sao auditaveis externamente. Existe uma rotina de retrospectiva que alimenta melhorias
no proprio SOP-IA. A IA e avaliada como membro funcional do time com metricas de desempenho.

**Sinais Observaveis:**
- Existe um `benchmarks-historicos.md` com dados de pelo menos tres projetos passados
- A organizacao consegue responder "qual e o nosso Lead Time medio" sem buscar no calendario
- O SOP-IA foi alterado ao menos uma vez com base em uma retrospectiva documentada
- O Modelo de Rastreabilidade conecta objetivos de negocio a commits especificos de codigo

**Plano de Evolucao para Nivel 5:**
- Automatizar a coleta de metricas via GitHub Actions ou equivalente
- Implementar revisao de maturidade semestral com toda a lideranca

---

## Nivel 5 — Sistematizado
**Descricao:** O SOP-IA e auto-sustentavel. O proprio framework evolui com base em dados.
A IA contribui ativamente para a melhoria da metodologia. A organizacao consegue onboarding
de novos membros inteiramente via documentacao, sem depender de pessoas especificas.

**Sinais Observaveis:**
- O SOP-IA tem versoes com CHANGELOG e e tratado como software (com releases)
- Novos membros do time ficam produtivos em projetos sem Shadow de ninhum senior em menos de 48h
- O framework passou por auditoria externa ou revisao por pares de outra empresa
- Metricas de impacto sao coletadas automaticamente e disponibilizadas em dashboard

---

## Aplicacao para Este Time

**Perfil Atual:** Startup com 10 devs, projetos geralmente solos, ocasionalmente duplas ou squads.

**Nivel Estimado Atual:** 1 a 2 (baseado nos sintomas descritos: deploy instavel, deploys levando
dois dias por problemas de variaveis de ambiente e configuracao, ausencia de processo formal).

**Nivel Alvo para os Proximos 90 dias:** Nivel 3.

**Prioridade Imediata:** Implementar o `guia-de-deploy.md` e o `checklist-release.md`
para eliminar o principal ponto de dor identificado pela equipe.
