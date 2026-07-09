---
name: verificacao-antes-de-concluir
description: Use antes de afirmar que um trabalho está completo, corrigido ou passando nos testes, e antes de commitar ou abrir PR. Exige rodar os comandos de verificação e confirmar o output real antes de qualquer declaração de sucesso. Evidência antes de afirmação, sempre.
---

# Verificação Antes de Concluir

## Propósito

É comum declarar "está pronto" ou "os testes passam" sem de fato confirmar. Esta skill impõe uma checagem obrigatória de evidência antes de qualquer afirmação de conclusão.

## Quando usar

- Antes de dizer que um bug foi corrigido
- Antes de dizer que uma feature está completa
- Antes de commitar ou abrir um Pull Request
- Antes de qualquer frase do tipo "pronto", "funciona", "testes passando"

## Processo

1. **Identifique o comando de verificação correto.** Testes automatizados, build, lint, ou execução manual do fluxo afetado.
2. **Rode o comando de verdade.** Não presuma o resultado com base em ter lido o código. Execute.
3. **Leia o output completo.** Não pare no primeiro "PASS" se houver mais adiante no log. Confira se o número de testes rodados bate com o esperado.
4. **Se falhar, volte ao trabalho.** Não declare sucesso parcial como sucesso completo.
5. **Só então afirme conclusão, citando a evidência.** Em vez de "está funcionando", diga "rodei os 42 testes e todos passaram" ou "testei o fluxo X manualmente e o resultado foi Y".

## Diretrizes

- Nunca afirme que algo "deve funcionar" como se fosse "funciona confirmado". Se não rodou, diga que não rodou.
- Se o ambiente não permite rodar a verificação (falta de acesso, dependência ausente), declare essa limitação explicitamente em vez de assumir sucesso.
- Prefira mostrar o output relevante (ou um resumo fiel dele) a apenas afirmar o resultado.
- Isso vale tanto para código quanto para documentos, cálculos e qualquer entregável que tenha um jeito de ser conferido.

## Exemplo

**Errado:** "Corrigido o bug de validação de CPF, os testes devem passar agora."

**Certo:** "Corrigido o bug de validação de CPF. Rodei `npm test` e os 18 testes da suíte de validação passaram, incluindo o caso que estava falhando antes (`deve rejeitar CPF com dígito verificador inválido`)."
