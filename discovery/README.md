# discovery

**Fase de Descoberta do Projeto**

Esta pasta da a largada. Nenhuma linha de codigo deve ser escrita antes de todos os
artefatos aqui estarem preenchidos e aprovados pelo Sponsor.

## Para que serve
Responsavel por capturar o contexto completo do projeto: o problema de negocio, quem
resolve o que, quais acessos sao necessarios e como a IA vai operar. E o "contrato de
entendimento" entre o time tecnico e quem pediu o projeto.

## Quando executar
No inicio absoluto do projeto. Antes do repositorio de codigo ser criado.

## Beneficios
- Elimina assumpcoes nao documentadas que se tornam bugs de requisito
- Define o objetivo em uma frase testavel, nao em uma ideia vaga
- Mapeia acessos no dia zero, evitando bloqueios de sprint por token ou senha faltando
- Inicializa a IA com contexto real antes que ela comece a gerar codigo aleatório

## Sequencia de Execucao
1. `discovery-questions.md` — Responda as 11 perguntas com o Sponsor
2. `objective.md` — Escreva o objetivo em um paragrafo aprovado
3. `access-map.md` — Liste todos os acessos necessarios e seus status
4. `kickoff.md` — Consolide tudo e apresente ao time
5. `ai-prompt.md` — Injete o contexto no agente de IA
6. `raci.md` — (Se time com dois ou mais) Defina quem faz o que

## Criterio para Avan car
A fase esta concluida quando o Sponsor le o `kickoff.md` e diz: "e isso mesmo."
