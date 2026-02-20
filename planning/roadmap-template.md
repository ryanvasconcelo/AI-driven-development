# 🗺️ ROADMAP (SOP-IA)

## 1. O que é
A visão em altitude de cruzeiro (30.000 pés) do projeto. O Roadmap não detalha tarefas diárias, mas sim Épicos (Grandes Entregas) distribuídos ao longo do tempo (Semanas ou Meses).

## 2. Por que existe
Para gerenciar a expectativa do Sponsor. Quando o cliente pergunta "Quando a tela de exportação fica pronta?", o Tech Lead aponta para o Roadmap em vez de prometer uma data arbitrária. Para a IA, o Roadmap atua como limite de contexto: a IA não deve sugerir bibliotecas de exportação PDF na Semana 1 se isso só está previsto para a Semana 4.

## 3. Quando usar
Início da Fase 03 (Planejamento Operacional). Alimentado diretamente pela `matriz-de-priorizacao.md`.

## 4. Como usar passo a passo
1. Pegue os blocos priorizados da Fase 2.
2. Agrupe-os em "Milestones" (Marcos de Entrega).
3. Atribua durações realistas (lembre-se: desenvolvedores têm reuniões e ficam doentes. Multplique a estimativa técnica por 1.5).
4. Todo Roadmap deve ter um "Corte de MVP" claramente marcado.

## 5. Template Preenchível

```markdown
# Roadmap: [Nome do Projeto]

## 🎯 Milestone 1: Fundação & Parser Core (Semanas 1-2)
**Objetivo:** Fazer o sistema ler o arquivo base, interpretar as linhas em memória e não travar.
- [ ] Setup do Repositório Frontend (Vite/React).
- [ ] Leitura bruta do Txt via JS local (Zero API cloud).
- [ ] Extrator Regex para Blocos 0200, C170, C191.
- [ ] Mock de UI básica sem CSS (apenas console.log ou div simples).

## 🎯 Milestone 2: Motor Lógico de NCMs (Semanas 3-4)
**Objetivo:** Agrupar dados processados por imposto de forma humanamente legível.
- [ ] Lógica de Grouping (Joiner de C170 com itens 0200 pela NCM).
- [ ] Tratativa de Falhas (Sinais de Alerta no console para itens sem NCM nativas).
- [ ] Estilização Inicial Shadcn UI c/ Tailwind (Tema Dark Padrão).
- [ ] Renderização em Lista (Cards NCM).

## 🎯 Milestone 3: MVP - Interação Humana & Update Massivo (Semana 5)
*--- CORTE DE MVP ---*
**Objetivo:** Permitir ao contador injetar CST/Alíquotas e re-exportar resultados funcionais.
- [ ] Inserção de Inputs "Novo CST" em todos os Cards.
- [ ] Lógica Reversa: Writer local reconstruindo TXT com blocos C170 idênticos acrescidos de novos CSTs.
- [ ] Botão de "Exportar SPED Final".
- [ ] Onboarding visual explicativo aos contadores.

## 🎯 Milestone 4: Automação "De-Para" & Polish (Semana 6)
**Objetivo:** Evoluir para regras condicionais sem esforço estrito do contador.
- [ ] Componente React "Modal De-Para".
- [ ] Persistência localStorage da Regra do Cliente.
- [ ] IA/Engine local refatorando as 40.000 div's simultaneamente de PIS/COF.
```

## 6. Exemplos Reais
O roadmap real do SPED-PIS-COFINS foi executado quase exatamente seguindo esses 4 Milestones, evitando que o dev ficasse estressado com animações CSS do Tailwind (Milestone 2) enquanto o Parser Central (Milestone 1) ainda não existia.

## 7. Métricas Associadas
- **Atraso de Milestone:** Semanas de diferença entre o planejado e o executado.
- **Sobrevivência do MVP:** O "Corte de MVP" precisou ser empurrado para o Milestone 4? (Grave erro de escopo).

## 8. Perguntas de Validação
- Se o Milestone 1 atrasar, todos os outros atrasam automaticamente ou há trabalho paralelo possível?
- O Milestone final representa um ganho quantitativo para o usuário final que ele possa testar em tela?

## 9. Checklist de Conformidade
- [ ] O Milestone do MVP (MvP Cut) está desenhado graficamente ou textualmente no Roadmap?
- [ ] O projeto foi quebrado em entregas que não superam ciclos maiores de 3 semanas sem validação Humana?

## 10. Erros Comuns
- **Roadmap Água-Viva:** Milestones genéricos como "Fase de Backend" e "Fase de Frontend". Usuários não conseguem testar e aprovar um backend desconectado. Entregue fatias verticais (Backend + Front do mesmo módulo).
