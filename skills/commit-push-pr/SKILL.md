---
name: commit-push-pr
description: Fluxo completo e interativo de finalização de trabalho em Git — análise de diff, mensagem de commit no padrão Conventional Commits, push para o remoto e abertura de Pull Request em modo rascunho via GitHub CLI. Use sempre que o usuário pedir para commitar, "fechar a feature", "subir o código", "abrir PR", "finalizar o branch", ou qualquer variação do fluxo commit → push → PR. Cada etapa exige confirmação explícita antes de executar comandos que alteram o estado do repositório.
---

# Commit → Push → PR

## Propósito

Padronizar o encerramento de um ciclo de trabalho em Git, evitando commits mal descritos, pushes acidentais para o branch errado ou PRs abertos sem contexto. Cada etapa é um ponto de checagem, não uma sequência automática.

## Quando usar

- O usuário sinaliza que o trabalho está pronto para ser commitado
- Pedido explícito de commit, push ou PR
- Fim de uma sessão de desenvolvimento com mudanças pendentes

## Processo

1. **Analisar o diff.** Rode `git status` e `git diff` para entender exatamente o que mudou. Nunca commit às cegas.
2. **Propor a mensagem de commit.** Use o padrão Conventional Commits (`feat:`, `fix:`, `refactor:`, `docs:`, `test:`, `chore:`). Mostre a mensagem proposta e peça confirmação antes de rodar `git commit`.
3. **Confirmar o push.** Antes de `git push`, confirme o branch de destino. Se for a primeira vez que o branch é enviado, avise que será criado um branch remoto novo.
4. **Abrir o PR em modo rascunho.** Use `gh pr create --draft` com título e corpo gerados a partir do diff e da mensagem de commit. Rascunho por padrão, nunca PR pronto para review sem confirmação explícita.
5. **Confirmar cada etapa separadamente.** Commit, push e PR são três decisões, não uma. O usuário pode querer parar em qualquer uma delas.

## Diretrizes

- Nunca execute `git commit`, `git push` ou `gh pr create` sem confirmação explícita do usuário para aquela etapa específica.
- Se o diff incluir arquivos que parecem não deveriam ser commitados (`.env`, chaves, arquivos temporários), avise antes de prosseguir.
- Se o branch atual for `main` ou `master`, pare e pergunte se o usuário realmente quer commitar direto nele.
- Mensagens de commit devem descrever o "porquê", não apenas o "o quê".

## Exemplo de mensagem de commit

```
feat: adiciona validação de CPF no formulário de cadastro

Implementa verificação de dígitos verificadores antes do envio,
evitando submissões inválidas que hoje só são pegas no backend.
```
