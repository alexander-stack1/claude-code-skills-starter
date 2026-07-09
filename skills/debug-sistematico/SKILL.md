---
name: debug-sistematico
description: Use ao encontrar qualquer bug, falha de teste ou comportamento inesperado, antes de propor correções. Reproduz, isola, diagnostica e só então corrige. Evita o padrão de tentar soluções aleatórias sem entender a causa raiz.
---

# Debug Sistemático

## Propósito

Corrigir sem entender é apostar. Esta skill impõe uma sequência disciplinada antes de qualquer alteração de código: reproduzir o problema, isolar a causa, diagnosticar com evidência, e só então corrigir.

## Quando usar

- Bug reportado, com ou sem stack trace
- Teste falhando
- Comportamento diverge do esperado sem causa óbvia

## Processo

1. **Reproduzir.** Antes de qualquer coisa, confirme que consegue reproduzir o problema de forma consistente. Se não conseguir reproduzir, o próximo passo é descobrir por que não reproduz, não tentar corrigir um sintoma que não foi confirmado.
2. **Isolar.** Reduza o problema ao menor caso possível. Remova variáveis até sobrar só o que causa a falha.
3. **Formular hipótese.** Com base no que foi isolado, proponha uma explicação específica e testável para a causa, não um palpite genérico.
4. **Testar a hipótese com evidência.** Rode um comando, adicione um log, ou escreva um teste que confirme ou refute a hipótese antes de mexer na lógica principal.
5. **Corrigir a causa raiz, não o sintoma.** Se a correção só faz o sintoma sumir sem explicar por que a causa existia, volte ao passo 3.
6. **Verificar a correção.** Rode o caso reproduzido do passo 1 de novo. Só então considere o bug resolvido.

## Diretrizes

- Nunca proponha uma correção antes de ter uma hipótese testada sobre a causa.
- Se duas hipóteses parecem plausíveis, teste a mais específica primeiro, não a mais fácil de corrigir.
- Documente o que foi descartado. Isso evita repetir a mesma tentativa depois.
- Evidência antes de afirmação: não declare "encontrei o bug" sem ter confirmado com um teste ou log real.

## Anti-padrões a evitar

- Trocar código "para ver se resolve" sem entender por quê
- Corrigir o primeiro erro visível no stack trace sem verificar se é a causa ou uma consequência
- Declarar o bug resolvido só porque o erro específico sumiu, sem rodar o cenário original completo
