# ❓ PERGUNTAS OBRIGATÓRIAS (SOP-IA)

## 1. O que é
Um roteiro inflexível que deve ser respondido por escrito (ou transcrito de reunião) antes que qualquer esboço de arquitetura seja feito. 

## 2. Por que existe
Para combater o "Vamos começar a codar e a gente descobre no caminho". Desenvolvedores costumam preencher lacunas de negócio com suposições técnicas, resultando em retrabalho. Estas perguntas forçam o Stakeholder a declarar 100% das assunções.

## 3. Quando usar
Na primeira interação com o Cliente/Stakeholder Interno (Fase 01). As respostas alimentam diretamente o `escopo-template.md`.

## 4. Como usar passo a passo
1. Marque uma reunião ou envie assincronamente.
2. Não aceite respostas genéricas como "Tem que ser rápido" (Qual a métrica de rápido?).
3. Pegue a transcrição da reunião (como feito no SPED) e passe para a IA com o prompt: "Extraia as respostas exatas para o roteiro abaixo".
4. Salve o arquivo nesta pasta.

## 5. Template Preenchível (O Questionário)

```markdown
### Bloco 1: A Dor Principal
1. Descreva o processo exato que ocorre hoje, sem a nova solução. Onde ele quebra?
2. Se este projeto falhar miseravelmente, qual é a principal métrica que vai doer na empresa?
3. Se o projeto for um sucesso absurdo, o que muda na vida do usuário final imediatamente?

### Bloco 2: Escopo e Fronteiras
4. O que a solução definitivamente NÃO deve fazer? (Ex: "Não precisa de app mobile", "Não envia e-mails sozinhos").
5. Quem são os usuários reais e qual o nível técnico deles? (Ex: "Atendentes exaustos", "Contadores detalhistas").
6. Qual o cenário de uso mais crítico (O "Happy Path")?

### Bloco 3: Dados e Integrações
7. Onde estão os dados? (Excel local, API do cliente, BD legado?).
8. Quais credenciais são necessárias e quem tem a chave?
9. Os dados são sensíveis? Podem transitar pela nuvem? (Se não, a solução deve ser Client-Side/Offline).

### Bloco 4: Restrições Inegociáveis
10. Qual a data fatal? Por que essa data?
11. Existe alguma restrição tecnológica? (Ex: "A infra da empresa só aceita C#", "Tem que rodar no Chrome antigo").
```

## 6. Exemplos Reais
No projeto SPED, as respostas 7 e 9 definiram toda a arquitetura. O cliente informou que os dados eram "SPEDs gigantescos" e que "não poderiam ser salvos na web por questões fiscais". Isso forçou a equipe arquitetural (IA + Dev) a escolher uma stack 100% local (Vite/React com FileReader API), descartando semanas de trabalho inútil em bancos de dados.

## 7. Métricas Associadas
- **Completude do Discovery:** 11/11 perguntas respondidas com dados mensuráveis.
- **Redução de Dúvidas Técnicas:** Quantidade nula de "Será que eles preferem a cor azul ou vermelha?", pois tudo está rastreado.

## 8. Perguntas de Validação
- Se eu entregar esse documento mastigado para um dev júnior hoje, ele sabe *exatamente* o campo de batalha?
- Há alguma chance da IA "alucinar" um requisito fora destas respostas?

## 9. Checklist de Conformidade
- [ ] O roteiro foi preenchido e comitado no repo?
- [ ] O Stakeholder principal concordou com as nuances?
- [ ] O documento gerou a matriz do `levatamento-acessos.md`?

## 10. Erros Comuns
- Mandar um formulário frio de 40 perguntas em vez destas 11 vitais.
- Aceitar que o projeto não possui "restrições". Sempre existem prazos, bolsos ou servidores inegociáveis.
