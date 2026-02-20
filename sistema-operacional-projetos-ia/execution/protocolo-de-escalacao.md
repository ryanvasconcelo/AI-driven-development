# PROTOCOLO DE ESCALACAO (SOP-IA v2.0)

## O que e
O fluxo estruturado para resolver impasses, conflitos tecnicos e bloqueios que o
desenvolvedor ou o agente de IA nao conseguem resolver autonomamente.

## Por que existe
Sem um protocolo, impasses tecnicos se tornam conversas circulares que consomem horas
sem resolucao. A IA pode ficar presa tentando infinitamente resolver um problema fora
da sua capacidade ou escopo sem sinalizar que precisa de intervencao humana.

## Nivel de Maturidade Minimo: 2
## Modo de Operacao: Todos

---

## Fluxo de Escalacao por Tipo de Impasse

### Tipo 1 — Impasse Tecnico (A IA nao sabe como resolver)
Sinais: O agente tenta a mesma abordagem mais de 3 vezes sem sucesso; o erro persiste
apos a correcao esperada; a IA sugere solucoes contraditorias.

**Protocolo:**
1. O agente deve PARAR, registrar o contexto do impasse (mensagem de erro, tentativas feitas)
2. Apresentar ao dev: "Atingi um limite tecnico. Aqui esta o contexto. Qual a sua decisao?"
3. O dev analisa e decide: resolver manualmente, buscar documentacao externa, ou
   reformular a abordagem
4. A resolucao e registrada em um ADR se envolver mudanca arquitetural

### Tipo 2 — Conflito de Escopo (O pedido contradiz o escopo aprovado)
Sinais: O dev ou cliente pede algo que nao esta no In-Scope; a feature solicitada
contradiz uma restricao do Out-of-Scope.

**Protocolo:**
1. O agente deve RECUSAR a implementacao e explicar o conflito
2. Apresentar: "Este pedido contradiz o escopo aprovado em [item X]. Para prosseguir,
   abra um Change Request formal no `controle-de-mudancas.md`."
3. O Sponsor decide se aprova o CR ou mantem o escopo original

### Tipo 3 — Bloqueio por Dependencia (Espera por acesso ou pessoa)
Sinais: Deploy bloqueado por token nao disponivel; task bloqueada por feedback de
stakeholder que nao respondeu.

**Protocolo:**
1. Registrar o bloqueio no `task.md` com marcador `[BLOQUEADO: motivo]`
2. Escalar via canal de comunicacao acordado (email, Slack) com prazo de resposta esperado
3. Se o bloqueio superar 2 dias: o tech lead resolve substituindo a dependencia
   (mock, stub, ou remodelagem de arquitetura)
4. Nunca paralisar o projeto; reorder o backlog e trabalhar no proximo item de maior ICE Score

### Tipo 4 — Conflito entre Dev e IA (O dev discorda da sugestao tecnica)
Sinais: A IA recomenda uma arquitetura ou biblioteca que o dev discorda; a IA insiste
numa abordagem que o dev considera inadequada.

**Protocolo:**
1. O dev tem a palavra final. Sempre. A IA e uma ferramenta, nao um stackeholder.
2. O dev documenta a decisao em um ADR: "IA sugeriu X. Decidimos Y pelo motivo Z."
3. O agente deve aceitar a decisao e adaptar sua execucao sem resistencia

---

## Indicadores de Uso Saudavel do Protocolo

- O protocolo e acionado 1 a 3 vezes por projeto: sinal de uso correto
- O protocolo NUNCA foi acionado: sinal de que a IA esta operando sem supervisao
- O protocolo e acionado mais de 10 vezes por Sprint: sinal de Escopo mal definido na Fase 2
