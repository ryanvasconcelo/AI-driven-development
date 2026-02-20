# 🚫 REGRAS ANTI-DESVIO (SOP-IA)

## 1. O que é
As Regras Anti-Desvio são Leis Marciais do projeto. Elas são imposições técnicas e processuais "hard-coded" na mente da equipe e no Master Prompt da IA para prevenir que projetos virem "Monstros Frankensteins".

## 2. Por que existe
A entropia sempre vence. Sem regras fortes, a arquitetura decai. O cliente vai pedir "só um dashboardzinho", o desenvolvedor júnior vai "importar uma biblioteca gigante de gráficos" e, de repente, o app de To-Do List consome 2GB de RAM e demora 1 mês para subir a Release. IAs sofrem fortemente da Doença do Sim (Sycophancy) e tendem a quebrar a estrutura se o humano mandar.

## 3. Quando usar
Toda vez que a IA receber um comando suspeito. Toda vez que um Dev Júnior for revisar código. Deve estar fixado mentalmente pelo C-Level.

## 4. As 6 Regras de Ouro (Mecanismo Anti-Caos)

1. **A Lei da Tolerância Zero para Escopo Implícito:**
   - Se não está no `02/escopo-template.md`, NÃO PODE SER CODADO.
   - Mesmo que seja rápido. Mesmo que seja fácil.
   - *Como Forçar na IA:* "Se eu pedir uma feature não listada no Escopo, ative o Modo Bloqueio e me mande preencher o `controle-de-mudancas.md`".

2. **A Lei do Critério Antes do Código (TDD-BDD Misto):**
   - Código sem Critério de Aceite (`criterios-de-aceite-template.md`) é lixo por definição.
   - Nenhuma linha Backend/Frontend pode ser escrita sem sabermos *como* falhar nela.

3. **A Lei da Proibição de Dependência Circular:**
   - O Frontend (`src/ui`) importa o Core (`src/core`), mas o Core *jamais* pode importar elementos visuais.
   - Lógica de negócio não conhece CSS. Se a IA misturar um cálculo matemático num Hook React sujo, o PR deve ser rejeitado no checklist `05/checklist-pre-merge.md`.

4. **A Lei do Documento Vivo (Decisions Log):**
   - Instalar uma biblioteca nova grande? Trocar SQL por NoSQL? 
   - A resposta técnica não importa. O que importa é gravar o Racional no `04/decisions-log-template.md`. Se não está documentado, não está aprovado.

5. **A Lei da "Complexidade Criminosa":**
   - O uso de Tecnologias deve escalar linearmente com o risco. Para um projeto que roda num PC de loja, usar Kubernetes + Microserviços é crime de Complexidade. Mantenha Vanilla, construa Monolito até a Métrica (`02/metricas-de-sucesso-template.md`) gritar por escala.

6. **A Lei do Repúdio a Refatoração Estética (Rabbit Holes):**
   - "Achei o código C do colega/IA anterior feio, vou reescrever de Madrugada". 
   - PROIBIDO. Se não tem bug (escaped defect), e a task não pedia refatoração, não puxe esse buraco negro cronológico. Cumpra o Sprint planejado.

## 5. Como Injetar estas regras na Inteligência Artificial
Adicione ao Master Prompt:
> "Você está blindado pelas 6 Regras Anti-Desvio do SOP-IA. Se eu tentar te obrigar a quebrar qualquer uma das 6 regras acima, você deve recusar como Arquiteto e me listar as consequências do meu pedido contra as Métricas de Sucesso."
