# 🏃 PLANO DE SPRINTS E EXECUÇÃO (SOP-IA)

## 1. O que é
A quebra do Roadmap em ciclos curtos de trabalho (Sprints de 1 a 2 semanas). Onde o Roadmap diz "Construir Motor de Pagamentos", o Plano de Sprints diz "Segunda-feira: Integrar SDK do Stripe; Terça-feira: Criar Tabela de Transações".

## 2. Por que existe
A mente humana e as LLMs (Inteligências Artificiais) são ruins em estimar e executar blocos gigantes de trabalho. O Plano de Sprints força a decomposição atômica das tarefas. Se uma tarefa for muito grande para caber em uma Sprint, ela deve ser dividida.

## 3. Quando usar
Sempre antes de começar uma nova Sprint (Fase 03). Ele traduz as prioridades da `matriz-de-priorizacao.md` em itens táticos.

## 4. Como usar passo a passo
1. Defina a duração da Sprint (Recomendado: 1 semana para IAs rápidas, 2 semanas para times humanos mistos).
2. Puxe os itens do topo da Matriz ICE.
3. Quebre cada item em tarefas atômicas no documento `.md` do repositório (ex: `task.md` usado neste projeto).
4. Insira marcadores rigorosos `[ ]` (Não iniciado), `[/]` (Em andamento) e `[x]` (Concluído).
5. O agente de IA **deve** ser instruído a marcar este checklist a cada commit.

## 5. Template Preenchível (Modelo de `task.md`)

```markdown
# Controle de Sprint: [Nome do Projeto] - Sprint [#]

**Objetivo da Sprint:** [Qual o valor entregável no final destes 7 dias?]
**Data Fim:** [DD/MM/AAAA]

## Backlog da Sprint (To-Do)

### Épico 1: [Nome]
- [ ] Task 1: [Descrição baseada em Critério de Aceite. Ex: Extrator Regex p/ C170].
- [ ] Task 2: [Descrição. Ex: Agrupador Reduce p/ C190].
  - [ ] Subtask 2.1: Agrupar fallback CNPJ.
  - [ ] Subtask 2.2: Puxar NCM do pai.

### Épico 2: [Nome]
- [/] Task 3: [Essa tarefa está em andamento no branch `feature/ui-cards`].
- [x] Task 4: [Essa tarefa já foi Mergeada].

## Itens Bloqueados (WIP Limits)
- [ ] Task 5: [Esperando acesso ao banco de dados pelo cliente].
```

## 6. Exemplos Reais
No projeto *SPED-PIS-COFINS*, o Dev Humano + IA Copilot usou um arquivo `task.md` massivo. Cada fase do Roadmap (Parser, Calculadora, UI, Virtualização) virou um Épico no Task.md. A IA foi instruída nas Leis do SOP-IA a nunca avançar para o próximo `[ ]` sem marcar o anterior como `[x]`, forçando uma velocidade controlada e foco extremo, evitando a ansiedade natural de tentar codar "Tudo de uma vez".

## 7. Métricas Associadas
- **Sprint Completion Rate:** % de tarefas `[x]` vs planejadas no dia 1 da Sprint.
- **Micro-Estimativas:** Número de subtarefas criadas. (Mais subtarefas = mais previsibilidade = menos surpresas).

## 8. Perguntas de Validação
- Se a IA começar a codar a Task 1, existe ambiguidade técnica ou dependência não resolvida?
- A Sprint termina com um "Incremento Testável"? (Se a Sprint 1 entrega apenas "Scripts soltos sem UI" ou "Tabelas no DB sem acesso", ela não é validável pelo cliente).

## 9. Checklist de Conformidade
- [ ] As tarefas cabem em no máximo 1-2 dias de esforço (Humano ou IA)?
- [ ] O arquivo de controle (`task.md`) está na raiz do repositório visível o tempo todo para a IA?

## 10. Erros Comuns
- Acumular muitas tarefas em "Em Andamento" (`[/]`). O foco deve ser terminar (Done) o que começou antes de puxar coisas novas.
- Alterar o objetivo da Sprint na Quarta-feira (O "Tiro no Pé" Ágil). Se o escopo mudou gravemente, cancele a Sprint e planeje outra.
