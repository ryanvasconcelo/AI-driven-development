# 📐 PADRÕES DE CÓDIGO (SOP-IA)

## 1. O que é
A constituição do código do projeto. Define nomenclatura, linting, idiomas dos commits e limites do Agente de IA.

## 2. Por que existe
Para manter a base de código previsível. Uma vez que humanos e dezenas de sessões diferentes de Inteligência Artificial vão contribuir com o projeto durante semanas, se não houver um Padrão Inflexível documentado, em 5 dias você terá botões criados em CSS puro, outros em Tailwind, nomes de variáveis em PT-br e BR-En misturados.

## 3. Quando usar
Junto com o `.eslintrc` no início do projeto. A IA deve ser instruída a ler isso sempre no Master Prompt.

## 4. Como usar passo a passo
Preencha as regras, aprove-as com o time humano.

## 5. Template Preenchível e Exemplos

```markdown
# Normas de Engenharia do Projeto

## 1. Nomenclaturas
- Nomes de Funções e Variáveis: `camelCase` (em inglês). Ex: `calculatePIS()`.
- Nomes de Arquivos React: `PascalCase`. Ex: `DeParaModal.jsx`. 
- Repita o nome da linguagem de negócio: Se o campo do SPED diz "COD_ITEM", crie `codItem`, não traduza para `productId`.

## 2. Paradigmas 
- O projeto prioriza Código Funcional puro. Evite `Classes` (POO).
- Evite aninhamentos terríveis (`callback hells`). Retorne cedo (Early Returns).

## 3. Mensagens de Commit
As mensagens devem dizer O QUE e POR QUE. Idioma oficial do repositório: Inglês ou Português.

## 4. Regras Absolutas para as IAs (Copilotos)
- É TERMINANTEMENTE proibido adicionar novas libs (`npm install x`) sem consultar os Humanos no Chat.
- Não altere as configs de Tailwind/Vite sem aprovação prévia.
- Mantenha log centralizado: use `logger` nativo ao invés de milhares de `console.log`.
```
