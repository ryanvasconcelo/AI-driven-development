# 🏛️ ARQUITETURA DO PROJETO (SOP-IA)

## 1. O que é
É o esqueleto técnico da aplicação. Define como os componentes em alto nível se comunicam, quais serviços externos são chamados, e as decisões de infraestrutura. Não é um diagrama detalhado de banco de dados, mas sim a visão a 10.000 pés da engenharia.

## 2. Por que existe
Para estancar o "Over-Engineering" da Inteligência Artificial. Se a IA é deixada agir livremente, ela tende a sugerir microserviços e Message Brokers para um sistema de To-Do list. A arquitetura fixa o contexto tecnológico do Copiloto.

## 3. Quando usar
Fase 04, logo antes do início da primeira Sprint executiva.

## 4. Como usar passo a passo
1. Avalie as Regras Mapeadas no "Out-of-Scope" e nas *Métricas de Risco* da Fase 2.
2. Escreva o fluxo básico de dados (Data Flow).
3. Liste as Tecnologias Chaves Inegociáveis.
4. (Opcional) Gere um bloco Mermaid.js text para visualização.

## 5. Template Preenchível

```markdown
# Arquitetura Macro: [Nome do Projeto]

## 1. O Padrão Arquitetural Escolhido
[Ex: Monolito Local Client-Side / API REST Node.js + React / Serverless Next.js]

## 2. Por que esta arquitetura e não outra?
[Justificativa de negócio. Ex: Escolhemos Client-Side puro porque a Métrica de Risco proíbe envio de notas fiscais pra nuvem.]

## 3. Stack Tecnológica Base
- **Frontend:** [React + Vite]
- **State Management:** [Context API (Sem Redux, pela simplicidade)]
- **UI Framework:** [Shadcn UI (Menor dependência de CSS proprietário)]
- **Backend:** [Não aplicável]
- **Storage:** [Navegador do Cliente (File API) + localStorage para perfil]

## 4. Diagrama de Fluxo de Dados 
[Se possível, cole um mermaid abaixo]
```

## 6. Exemplos Reais
O Projeto SPED adotou um formato de motor processador (Vanilla JS `core/`) injetado num Frontend Vit (React `UI/`). A arquitetura engessou propositalmente a separação para que as lógicas de cálculo PIS/COF não se misturassem com os estados do React.

## 7. Métricas Associadas
- **Complexidade vs Necessidade:** O número de serviços cloud propostos é proporcional à métrica de impacto?

## 8. Perguntas de Validação
- Estamos importando uma biblioteca de 50MB para resolver um problema que 10 linhas de Vanilla JS resolvem?
- A arquitetura está preparada para as métricas da Fase 2?

## 9. Checklist de Conformidade
- [ ] O modelo arquitetural respeita toda a restrição técnica mapeada pela Fase 1?
