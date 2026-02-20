# CONTRIBUTING — Como Contribuir com o SOP-IA

Este documento define as regras para evoluir o framework. O SOP-IA é tratado como software: tem versões, tem critérios de aceite para mudanças, e tem um responsável por aprovação. Contribuições sem seguir este processo não são incorporadas.

---

## Quem Pode Contribuir

Qualquer membro do time que tenha aplicado o SOP-IA em pelo menos um projeto real pode propor melhorias. Contribuições baseadas apenas em teoria, sem experiência prática de uso, são aceitas apenas como sugestões e vão para o backlog sem garantia de implementação.

---

## Tipos de Contribuição

### Tipo 1 — Correção (Patch)
Corrigir erro de português, link quebrado, inconsistência entre arquivos, campo faltando em template.

- Não exige aprovação prévia
- Abrir PR diretamente com a correção
- Título do PR: `fix: [descrição curta]`
- Incrementa versão PATCH (ex: v2.0.0 → v2.0.1)

### Tipo 2 — Melhoria de Artefato Existente (Minor)
Adicionar campo novo a um template, melhorar exemplo aplicado, adicionar pergunta de validação, refinar linguagem de um checklist.

- Exige abertura de Issue antes do PR descrevendo a melhoria e o motivo
- O Tech Lead do framework avalia e aprova a Issue antes da implementação
- Título do PR: `improve: [nome do artefato] — [descrição curta]`
- Incrementa versão MINOR (ex: v2.0.1 → v2.1.0)

### Tipo 3 — Novo Artefato ou Nova Fase (Major)
Adicionar novo arquivo ao framework, criar nova fase, alterar estrutura de pastas, mudar nomenclatura de artefatos existentes.

- Exige Issue aprovada + ADR documentando a decisão antes de qualquer implementação
- O ADR deve conter: contexto, alternativas consideradas, decisão tomada, consequências
- Deve ser validado em pelo menos um projeto real antes de ser incorporado ao framework
- Título do PR: `feat: [nome do novo artefato]`
- Incrementa versão MAJOR (ex: v2.1.0 → v3.0.0)

---

## Regras Absolutas

**1. Nenhuma mudança entra sem evidência de uso real.**
Se o artefato proposto não foi aplicado em pelo menos um projeto real da empresa, ele vai para o backlog como candidato, não como entrega. O framework não aceita teoria não testada.

**2. Compatibilidade retroativa é obrigatória em mudanças Minor.**
Um projeto que usa v2.0.0 não pode quebrar ao atualizar para v2.1.0. Se a mudança quebra compatibilidade, ela é Major.

**3. Mudanças de Major version exigem guia de migração.**
Qualquer mudança que torna artefatos anteriores obsoletos deve incluir um arquivo `migration/vX-to-vY.md` explicando como atualizar projetos existentes.

**4. O Tech Lead do framework tem veto.**
Mesmo que uma melhoria seja tecnicamente correta, ela pode ser vetada se contradizer os princípios fundamentais do SOP-IA (simplicidade progressiva, evidência antes de teoria, método sobre ferramenta).

**5. Nenhum artefato é deletado — apenas deprecado.**
Artefatos obsoletos são marcados com `[DEPRECADO em vX.Y.Z — substituído por arquivo.md]` e permanecem no repositório por pelo menos uma versão Major antes de serem arquivados.

---

## Fluxo de uma Contribuição Tipo 3 (Passo a Passo)

```
1. Usar o artefato proposto em um projeto real
2. Abrir Issue com: problema que resolve, como foi usado, resultado observado
3. Aguardar aprovação do Tech Lead (prazo máximo: 5 dias úteis)
4. Se aprovado: escrever ADR em architecture/adr.md documentando a decisão
5. Implementar o artefato seguindo os padrões de linguagem do framework
6. Abrir PR referenciando a Issue e o ADR
7. O Tech Lead revisa e aprova ou solicita ajustes
8. Merge na main + atualização do CHANGELOG + bump de versão
```

---

## Padrões de Linguagem e Formato

Todo artefato do SOP-IA segue a mesma estrutura de 10 seções:

```markdown
# [NOME DO ARTEFATO] (SOP-IA)

## 1. O que é
## 2. Por que existe
## 3. Quando usar
## 4. Como usar passo a passo
## 5. Template Preenchível
## 6. Exemplos Reais
## 7. Métricas Associadas
## 8. Perguntas de Validação
## 9. Checklist de Conformidade
## 10. Erros Comuns
```

Artefatos que não seguem esta estrutura não são aceitos. A uniformidade é o que permite que qualquer pessoa (ou IA) navegue o framework sem precisar de explicação.

**Linguagem:** Português técnico neutro. Sem gírias, sem abreviações informais, sem emojis nos arquivos de conteúdo (apenas no README principal onde indicado).

**Exemplos Reais:** Todo artefato deve conter pelo menos um exemplo baseado em projeto real da empresa. Exemplos genéricos ("Ex: um e-commerce qualquer") são aceitos apenas como complemento, nunca como o exemplo principal.

---

## O que Não Será Aceito

- Artefatos que duplicam funcionalidade de artefatos existentes sem substituí-los explicitamente
- Mudanças motivadas por preferência pessoal de ferramenta (ex: "prefiro Notion ao invés de Markdown")
- Adição de tecnologias específicas como requisito do framework (o SOP-IA é agnóstico a stack)
- Qualquer mudança que aumente a complexidade mínima de adoção sem aumentar proporcionalmente o valor entregue

---

## Responsável pelo Framework

**Tech Lead do SOP-IA:** Ryan Vasconcelo
**Canal de contato para Issues:** GitHub Issues deste repositório
**SLA de resposta:** 5 dias úteis para Issues, 10 dias úteis para PRs de Tipo 3
