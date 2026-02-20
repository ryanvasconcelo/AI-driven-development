# architecture

**Fase de Arquitetura e Organizacao Tecnica**

A fundacao tecnica do projeto. Define como o sistema e estruturado, quais tecnologias
sao usadas e como as decisoes sao documentadas para que qualquer pessoa (ou IA) possa
entender o projeto sem precisar perguntar.

## Para que serve
Previne o over-engineering. Fixa as tecnologias escolhidas. Padroniza o codigo.
Registra as decisoes arquiteturais com justificativa para que nao sejam revertidas
sem analise no futuro.

## Quando executar
Antes do primeiro commit de codigo funcional. Pode ser revisitada a cada mudanca
arquitetural significativa.

## Beneficios
- A IA para de sugerir microservicos para um sistema de 3 usuarios
- ADRs registram o "por que fizemos assim" antes que o time esqueça
- Os padroes de codigo garantem que codigo gerado por IA e humano pareca do mesmo autor
- A estrutura de pastas impede que logica de negocio vaze para componentes visuais

## Sequencia de Execucao
1. `architecture.md` — Stack, fluxo de dados, justificativa da escolha
2. `project-structure.md` — Estrutura de pastas e separacao de responsabilidades
3. `code-standards.md` — Nomenclatura, paradigmas, regras para a IA
4. `adr.md` — Registro incremental de todas as decisoes arquiteturais (um ADR por decisao)

## Criterio para Avancar
Um dev novo consegue entender a estrutura do projeto lendo apenas esta pasta em 30 minutos.
