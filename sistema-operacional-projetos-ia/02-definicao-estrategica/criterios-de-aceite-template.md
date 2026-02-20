# ✅ CRITÉRIOS DE ACEITE OBRIGATÓRIOS (SOP-IA)

## 1. O que é
A barreira matemática entre "Eu acho que terminei" e "O software está pronto para produção". Um Critério de Aceite (Acceptance Criteria - AC) define as condições exatas, testáveis e binárias (Pass/Fail) que uma funcionalidade deve cumprir para ser considerada concluída.

## 2. Por que existe
A maior causa de atrito entre Desenvolvedores e QA/Clientes é a assimetria de expectativa.
- O Cliente diz: "Quero que o sistema exporte o relatório".
- O Dev (Humano/IA) coda: Um botão que baixa um `.txt` simples.
- O Cliente reclama: "Mas eu queria um PDF com o logo da empresa e totalizadores no rodapé!"

Os Critérios de Aceite matam a ambiguidade. Se não está no critério de aceite, o Dev/IA NÃO deve programar.

## 3. Quando usar
Durante a Fase 02 (Definição Estratégica), para cada Módulo ou Funcionalidade listada no `escopo-template.md`.
Também usado diariamente na Fase 05 (Execução) pela IA/Copilot, que é instruída a ler este arquivo e gerar *Unit Tests* ou scripts de validação antes de começar a codar (TDD - Test Driven Development).

## 4. Como usar passo a passo
1. Pegue uma Funcionalidade do `escopo-template.md`.
2. Escreva o cenário no formato clássico BDD: `Dado que [Contexto], Quando [Ação], Então [Resultado Esperado]`.
3. Defina a *Forma de Validação* (Manual na Tela, Teste Automatizado Jest, Subagent QA).
4. Nomeie o responsável ou a Ferramenta que dará o carimbo de aprovado.
5. Ao concluir a tarefa, adicione o link ou path da *Evidência* (Screenshot, log do Cypress).

## 5. Template Preenchível

```markdown
# Critérios de Aceite: [Nome do Projeto]

## Funcionalidade 1: [Ex: Módulo "De-Para" de NCMs]
**Descrição:** O sistema deve permitir a substituição em lote de CSTs (PIS/COFINS) baseado em regras de NCM.

### Critério 1.1: Aplicação de Regra Exata
- **Contexto (Dado que):** O usuário possui no SPED um produto A (NCM 10063021) com CST atual "73" e cadastra a regra "Para NCM 10063021 e CST Atual 73 -> Novo CST 50".
- **Ação (Quando):** O usuário clica em "Salvar e Aplicar".
- **Resultado Esperado (Então):** O sistema deve atualizar TODOS os registros filhos deste NCM para o CST 50 e colorir o input de verde. Registros com CST "01" (diferente de 73) neste mesmo NCM NÃO devem ser alterados.
- **Forma de Validação:** UI Test Manual via Agent Browser QA.
- **Responsável:** QA (Neste caso, Automação `browser_subagent`).
- **Evidência:** [Deixar em branco até testar. Preencher com link do vídeo/screenshot: `rayo_final_depara_check_1771597772117.webp`]

### Critério 1.2: Tolerância a Falha de Arquivo Padrão
- **Contexto (Dado que):** O usuário seleciona um arquivo TXT não relacionado ao SPED (ex: boleto).
- **Ação (Quando):** O arquivo é dropado na Upload Zone.
- **Resultado Esperado (Então):** O sistema deve exibir um Toast de erro bloqueante com a mensagem "Arquivo SPED Inválido ou Corrompido" em menos de 1 segundo e não quebrar a aplicação (White Screen of Death).
- **Forma de Validação:** Console Error Handling.
- **Responsável:** Desenvolvedor/IA.
- **Evidência:** [ ]
```

## 6. Exemplos Reais
Ao criar o módulo "De-Para" no projeto SPED-PIS-COFINS, um critério de aceite (Critério 1.1 acima) forçou o agente de QA (`browser_subagent`) a abrir uma página localhost, importar dinamicamente o `TESTE_10_ITENS.TXT`, colocar uma regra "73 -> 50" no frontend, clicar em aplicar e confirmar visualmente que o feijão mudou o CST PIS e COF. A IA encontrou falhas exatamente porque o critério era cruel e exato, permitindo correções na engine de parser ANTES da entrega para o cliente.

## 7. Métricas Associadas
- **Cobertura de Critérios:** % de features no Escopo que possuem ao menos 1 AC mapeado.
- **Taxa de Rejeição de QA:** Quantas vezes o critério precisou ser retestado (Indica AC mal escrito ou código mal feito).

## 8. Perguntas de Validação
- O Critério de Aceite utiliza palavras vagas como ("rápido", "bonito", "intuitivo")? Se sim, está incorreto. Troque para "Responde em menos de 200ms", "Segments UI Library", "Máximo de 3 cliques".
- A IA pode transformar o critério 1.1 em um teste automatizado Jest agora mesmo?

## 9. Checklist de Conformidade
- [ ] Todo requisito não-funcional (segurança, performance) virou um critério de aceite?
- [ ] O cliente concorda que se estes cenários passarem, ele paga a fatura?

## 10. Erros Comuns
- **Critérios Tecnológicos:** "Dado que estou usando React Context, a store Redux deve...". O Cliente não se importa com Redux. Critérios descrevem Comportamento do Sistema, não arquitetura subjacente.
- **Deixar para pensar no AC depois de codar:** Desenvolver sem AC leva o desenvolvedor a escrever o AC para passar no código que ele acabou de construir, enviesando toda a qualidade.
