# 🗂️ ESTRUTURA BASE DE PROJETO (SOP-IA)

## 1. O que é
A matriz de arquivos e diretórios que padroniza ONDE cada coisa vive dentro do repositório Git.

## 2. Por que existe
Se você não diz para a IA (ou para o Dev Júnior) onde as coisas moram, eles colocarão Lógica de Negócios dentro dos Botões de UI, Regras de Banco de Dados dentro das Actions HTTP, etc. A padronização da raiz obriga o "Separation of Concerns" (Separação de Preocupações).

## 3. Quando usar
No `Day-0`, logo após dar o `git init`.

## 4. Como usar passo a passo
1. Rode um script de scaffold (ex: `mkdir -p docs src/core src/ui tests`).
2. Cole o arquivo README de navegação na raiz para que novos tripulantes (humanos ou artificiais) entendam a planta baixa da casa.

## 5. Template Preenchível e Estruturas Ouro

```markdown
# Estrutura Mestre Orientada a IA

```text
/
├── docs/                      # Todos os artefatos do SOP-IA criados nas Fases 01 a 04 devem estar aqui.
│   ├── adrs/                  # Decision Logs
│   └── requisitos/            # Escopo, Metricas, Kickoff
├── src/
│   ├── core/                  # Regras de Negócios puras. Vanilla JS/Python/TS. ZERO dependência visual.
│   │   └── calculator.js      # O motor do carro.
│   ├── ui/                    # A carroceria. Tudo relacionado a Telas (Vue, React, Swift).
│   │   ├── components/        # Pedacinhos reutilizáveis (Botões, Cards).
│   │   └── hooks/             # Ligações lógicas.
│   └── infra/                 # Escapamento. Onde o sistema toca no mundo (APIs, BD, File System).
├── tests/                     # Tão importante que fica na raiz. Contém Unit/E2E tests.
├── SOP_README.md              # O Master Prompt e Regras Locais do projeto.
```

## 6. Exemplos Reais
Ao isolar o Parser SPED (`core/sped-parser.js`) total da Tela e Layout no projeto base, garantiu-se que o motor que calcula Bilhões em impostos pudesse ser re-utilizado amanhã em um servidor Backend AWS, caso a empresa resolva deixar a solução Local `(Client-Side)`. A IA forçou rigorosamente os `styles.css` a viver longe da camada calculista.

## 7. Métricas Associadas
- **Acoplamento Inadequado:** A regra de ouro é "A camada X deve morrer, e a camada Y ainda deve continuar de pé". 

## 8. Perguntas de Validação
- Se eu trocar minha biblioteca gráfica de Tailwind para SCSS amanhã, o `core` para de calcular a base do imposto? Se sim: a estrutura falhou.
- Um script visual na UI pode quebrar os Unit Tests Centrais de Core Data Processors?

## 9. Checklist de Conformidade
- [ ] O `.gitignore` esconde arquivos confidenciais da pasta mestre?
- [ ] Módulos UI ignoram a existência de integrações backend diretas?

## 10. Erros Comuns
- "Salsichamento Sistêmico". Deixar componentes do React/Angular varrerem os bancos de dados. A IA adora escrever o Select SQL dentro da página de Roteamento para poupar tempo se não bloqueada aqui.
