# 🔬 PLANO DE VALIDAÇÃO (SOP-IA)

## 1. O que é
A rotina humana/automatizada que garante que a junção de vários Critérios de Aceite (Features) compõe uma Release utilizável. Validação é diferente de Teste de Código. Testar o código é saber se ele compila; Validar é saber se ele resolve a vida do usuário.

## 2. Por que existe
Para impedir que projetos passem em "100% dos testes de código" mas falhem miseravelmente na mão do cliente real porque o fluxo (User Journey) não faz sentido ou exige 15 cliques.

## 3. Quando usar
Sempre antes de enviar uma Release (Entrega grande) para o Sponsor. 

## 4. Como usar passo a passo
1. Abra este documento ao concluir as tasks do Sprint.
2. Defina os Cenários Fim-a-Fim (End-to-End).
3. Execute o Caminho Feliz (Happy Path).
4. Execute o Caminho Desastroso (Unhappy Path).
5. O Engenheiro Líder e o Cliente dão o aceite visual.

## 5. Template Preenchível

```markdown
# Validação Release 1.0: [Nome do Projeto]

### Cenário 1: Happy Path (A Jornada Perfeita)
- **Passo 1:** O Usuário abre o App e solta um arquivo TXT de 50MB válido.
- **Passo 2:** O App processa em menos de 3 segundos e exibe a lista de Grupos NCM.
- **Passo 3:** O Usuário insere "CST 50" em um Card pai e a tabela reflete instantaneamente nos C170 associados.
- **Passo 4:** O Usuário exporta. O arquivo TXT final passa no Validador Oficial SEFAZ.
- **Status da Validação:** [ ] Pendente | [x] Aprovado (Video Link/Screenshot)

### Cenário 2: Unhappy Path (Tudo deu Errado)
- **Passo 1:** O Usuário solta um PDF de 100MB na zona de arquivos SPED.
- **Passo 2:** O App NÃO trava. Exibe aviso: "Apenas arquivos .TXT são suportados."
- **Passo 3:** O Usuário recarrega a página no meio de uma edição sem salvar.
- **Passo 4:** O App reseta o Estado (Redux/State) graciosamente e pede o arquivo novamente.
- **Status da Validação:** [ ] Pendente | [x] Aprovado.
```

## 6. Exemplos Reais
No SPED-PIS-COFINS, nós usamos uma imagem (Screenshot Test) da Interface Polida de Onboarding e Validações massivas nos consoles. Quando um cenário falhava, o Agente autônomo pausava, refatorava o CSS ou o JS na branch de execução e gerava os assets atualizados antes de pedir aval.

## 7. Métricas Associadas
- **Bugs em Homologação:** Número de defeitos encontrados *após* a IA/Dev afirmar que estava "Pronto para o Usuário".
- **Tempo de Refatoração Tardia:** Horas reescrevendo fluxos confusos após reclamação de cliente.

## 8. Perguntas de Validação
- Se um usuário comum abrir a sua interface sem o desenvolvedor atrás dele explicando onde clicar... ele consegue fazer o Happy Path sozinho?
- Os Testes Visuais abrangeram cenários obscuros (ex: o usuário desligar a internet no meio da execução em módulos cloud)?

## 9. Checklist de Conformidade
- [ ] O Happy Path foi testado por alguém fora do time de Dev/IA?
- [ ] Houve um "Walkthrough" formal documentado para bater a meta e comprovar a validação antes da entrega?

## 10. Erros Comuns
- "A IA rodou o Cypress e tudo passou, então a validação está ok". O Cypress não detecta que a cor do botão primário está sumindo num monitor barato. O fator humano valida a utilidade da Feature.
