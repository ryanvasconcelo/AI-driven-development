# 🏁 TEMPLATE KICKOFF (SOP-IA)

## 1. O que é
O documento de "Aperto de Mão" formal. Ele sintetiza as Respostas Obrigatórias, a Definição do Objetivo e o Repositório de Acessos em uma única página que todos os C-Levels e Devs assinam mentalmente no dia 1.

## 2. Por que existe
Para garantir que a TI não construiu um trator quando o cliente pediu uma bicicleta. Stakeholders tendem a esquecer o que pediram 30 dias depois. O Kickoff é o registro da expectativa inicial consolidada.

## 3. Quando usar
A Reunião de Kickoff marca o fim da Fase 01 (Início) e o início da Fase 02 (Definição Estratégica).

## 4. Como usar passo a passo
1. Consolide os documentos `01-inicio-do-projeto`.
2. Preencha os campos macros abaixo.
3. Apresente em uma reunião de 15 minutos.
4. Salve a transcrição ou a gravação junto a este doc no repositório.

## 5. Template Preenchível

```markdown
# Kickoff: [Nome do Projeto]
**Data:** [DD/MM/AAAA]
**Sponsor (Quem Paga/Aprova):** [Nome]
**Engenheiro/Arquiteto Lider:** [Nome]

## 🎯 O Objetivo (Elevator Pitch)
[Cole do `definicao-de-objetivo.md`]

## ⚠️ O Que Decidimos NÃO Fazer (Limites)
[Cole os itens "fora do escopo" das `perguntas-obrigatorias.md`]

## 🛠️ Stack Tecnológica Presumida
- **Linguagem/Framework:** [Ex: React/Vite]
- **Infra/Deploy:** [Ex: Vercel / Nenhuma (Local)]
- **Bancos:** [Ex: PostgreSQL / Nenhum]

## 📅 Timeline Macro (Expectativa)
- **Fase 02 (Desenho):** [Data] a [Data]
- **Fase 03 (MVP):** [Data] a [Data]
- **Fase 04 (Piloto):** [Data] a [Data]

## ✅ Próximos Passos
1. Desenhar a Arquitetura Final.
2. Definir Critérios de Aceite no detalhe.
3. Iniciar Setup de Acessos Pendentes.
```

## 6. Exemplos Reais
No SPED-PIS-COFINS, o Kickoff foi a transcrição brutal e honesta da reunião com o contador (`transcricao_reuniao.txt`). O documento resumiu: Stack = Vanilla JS/React; Objetivo = Auditar SPEDs de dezenas de megabytes sem travar; Limite = Nada sobe pra nuvem.

## 7. Métricas Associadas
- **Alinhamento do Sponsor:** O Sponsor discordou de algo na leitura deste documento? (Se não leu e apenas disse "ok", é um risco red-flag 🔴).

## 8. Perguntas de Validação
- O documento aponta claramente QUEM é o "Sponsor" que tem a palavra final para desempatar discussões de escopo?

## 9. Checklist de Conformidade
- [ ] O Kickoff foi lido em voz alta na reunião inicial?
- [ ] O Stakeholder confirmou as restrições (O que NÃO vamos fazer)?

## 10. Erros Comuns
- Usar o Kickoff para detalhar tarefas de código (Jira Boards). Kickoff é sobre o QUÊ e PORQUÊ, não sobre o COMO. O COMO é Fase 4.
