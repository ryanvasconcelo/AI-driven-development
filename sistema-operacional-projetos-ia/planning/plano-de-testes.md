# 🧪 PLANO DE TESTES (SOP-IA)

## 1. O que é
É a estratégia técnica para provar que o código (as engrenagens) funciona perfeitamente isolado e também em conjunto com outras peças do software. Enquanto a Validação (Plano de Validação) foca no "O quê" (A jornada do usuário), os Testes focam no "Como" (O código aguenta 10 mil itens?).

## 2. Por que existe
O medo trava a inovação. Um sistema sem testes automatizados fará com que qualquer programador (humano ou IA) hesite em refatorar um arquivo grande pelo risco de quebrar outra coisa no processo sem perceber. Testes fornecem uma rede de proteção.

## 3. Quando usar
Junto com o desenvolvimento. Sendo realista: a escrita de Testes (Unitários/Integração) costuma ser abandonada por equipes com "pressa". Ao exigir que a Inteligência Artificial, atrelada por esta diretriz, gere os Unit Tests **antes** do código ou **logicamente atrelado a ele**, o sistema nunca envelhece de forma assustadora.

## 4. Como usar passo a passo
1. Determine que tipo de Teste será usado na camada. Exemplo: Para o motor matemático, Jest (`unit`). Para a interface React, Testing Library.
2. Escreva o `arquivo.test.js` e aponte no Terminal o resultado.
3. Não aceite _Commit_ / _Merge_ se o teste base quebrar.
4. Escreva no Prompts de IA para ela obrigatoriamente validar todo script crítico (ex: _"Prove matematicamente numa execução Node local isolada que o array [NCMs] de entrada agrupa apenas Chaves Únicas."_ - Vide `debug.mjs` criado no Projeto SPED).

## 5. Template Preenchível e Exemplos
Se for usar IA para automatizar esta fase, injete no prompt:

```javascript
/* Plano de Teste Unitário (Jest/Mocha format) */
describe('Módulo Parser SPED EFD', () => {

  it('deve extrair a linha C170 e quebrar em array de campos pelo |', () => {
    const rawLine = '|C170|01||1234567|DESC|1.00000|UN|...';
    const fields = parseLine(rawLine);
    expect(fields[4]).toBe('1234567');
  });

  it('não deve quebrar o sistema se o TXT vier vazio', () => {
    expect(() => parseSpedFile('')).not.toThrow();
  });

});
```

## 6. Exemplos Reais
Ao debuggar as regras do **De-Para no SPED-PIS-COFINS**, o Desenvolvedor IA (`Antigravity Agent`) ficou confuso com a descrição que caía sempre como "NCM Inválido" para itens C191. O teste isolado matemático forçou a IA a criar um loop `debug.mjs` autônomo. O teste apontou que o C190 pai possuía as tags certas. O teste salvou 5 horas de interface bugada mostrando que o erro estava no Motor e não na Tela.

## 7. Métricas Associadas
- **Code Coverage (Cobertura de Código):** % de linhas de código que são engatilhadas por testes automáticos (Ideal: Mínimo de 60% para MVPs críticos. 80% para Financeiros).

## 8. Perguntas de Validação
- Se eu mudar o cálculo de base PIS na camada Core `calculator.js`, os componentes do card na interface `NcmGroupCard.jsx` vão estourar um erro se eu rodar os testes agora mesmo? Se a resposta for não, o teste de integração é deficiente.

## 9. Checklist de Conformidade
- [ ] O pipeline CI/CD (GitHub Actions / Husky Pre-Commit) está bloqueando código sem testes automáticos?
- [ ] A IA foi instruída explicitamente a gerar pelo menos testes para a funcionalidade "caminho-feliz"?

## 10. Erros Comuns
- "Testar UI de botão mudando de cor". Não torre tempo testando estilos. Teste Lógica de Negócios e Matemática de Dados. Evite os "Flaky tests" visuais.
