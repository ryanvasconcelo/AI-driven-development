# 📅 CHECKLIST DIÁRIO (SOP-IA)

## 1. O que é
A rotina de "Bom dia" do projeto. Diferente da Daily Scrum (que diz o que foi feito), este checklist diz ao Desenvolvedor (ou ao Agente de IA) como "Carregar o Contexto" para não fazer bobagem naquele dia.

## 2. Por que existe
A IA sofre de amnésia de contexto em chats muito longos. Um desenvolvedor humano esquece a prioridade no meio da semana. Forçar a leitura diária dos artefatos base impede que o barco desvie um milímetro.

## 3. Quando usar
A primeira coisa que o Dev / Agente IA deve fazer ao ser acionado no projeto em uma nova sessão.

## 4. Como usar passo a passo
1. Abra este arquivo.
2. Marque mentalmente ou em log as validações.
3. Se houver Dívida Técnica (Tech Debt) de ontem, pague-a primeiro.

## 5. Template Preenchível e Executável

```markdown
# Checklist Diário de Contexto

Se você é uma Inteligência Artificial, LEIA ISSO E CONFIRME a cada nova sessão:

- [ ] **1. Eu li a Matriz ICE (`02/matriz-de-priorizacao.md`) hoje?** Eu sei exatamente qual é a Tarefa 1 do dia?
- [ ] **2. Eu li o `task.md` na raiz?** Eu sei quais tarefas estão `[/]` e precisam ser terminadas antes de eu sugerir puxar uma nova `[ ]`?
- [ ] **3. Os Critérios de Aceite da tarefa atual estão claros?** (Não codifique se a resposta for N/A).
- [ ] **4. Eu testei meu último commit?** Ou deixei código quebrado pra trás?
- [ ] **5. Alguém pediu mudança de Escopo ontem?** Se sim, o `05/controle-de-mudancas.md` foi preenchido?
```

## 6. Exemplos Reais
Ao religar o Agente Antigravity no dia seguinte para a Fase 3 do SPED, a IA foi forçada a ler o `task.md`. Lá estava marcado que o "Agrupamento NCM" já havia sido concluído `[x]`, então a IA sabia que deveria iniciar o Design da Modal sem precisar que o humano a guiasse desde o começo.

## 7. Métricas Associadas
- **Rápida Retomada (Time-To-Context):** Tempo que leva para um novo dev/IA começar a produzir num projeto abandonado há 3 meses. (Com este log, cai de 1 semana para 1 hora).

## 8. Perguntas de Validação
- O desenvolvedor abre a IDE e olha o GitHub Issues/Task.md antes do WhatsApp? Se sim, o SOP está funcionando.

## 9. Checklist de Conformidade
- [ ] O Prompt Inicial (Master Prompt) exige que a IA cheque este arquivo ao "acordar"?

## 10. Erros Comuns
- Tentar automatizar isso sem reflexão. O objetivo deste checklist é engajar o Córtex Frontal (ou as Layers de Reasoning da IA), não apertar botões no JIRA.
