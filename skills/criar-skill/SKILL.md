---
name: criar-skill
description: Cria novas skills do Claude Code com estrutura adequada (frontmatter, hierarquia de arquivos, descrição bem calibrada para disparo correto). Use quando o usuário pedir para "criar uma skill", "fazer uma skill nova", "transformar isso em skill", "automatizar esse processo como skill", ou quando estiver estruturando pela primeira vez um padrão de trabalho recorrente.
---

# Criar Skill

## Propósito

Uma skill mal escrita não dispara quando deveria, ou dispara demais e atrapalha. Esta skill guia a criação de novas skills do Claude Code com foco no que mais importa: a qualidade da `description`, porque é ela que determina se a skill é encontrada na hora certa.

## Estrutura mínima de uma skill

```
nome-da-skill/
└── SKILL.md
```

Skills mais complexas podem incluir arquivos auxiliares (scripts, templates, referências), mas o `SKILL.md` é obrigatório e é o único arquivo lido para decidir se a skill dispara.

## Anatomia do SKILL.md

```markdown
---
name: nome-da-skill
description: [ver seção abaixo — esta é a parte mais importante do arquivo]
---

# Nome da Skill

## Propósito
[por que essa skill existe, que problema ela resolve]

## Quando usar
[cenários concretos de disparo]

## Processo
[passos numerados, específicos, acionáveis]

## Diretrizes
[regras, restrições, anti-padrões]

## Exemplo
[pelo menos um exemplo concreto de uso correto]
```

## Como escrever uma boa description

A `description` é o único texto usado para decidir se a skill dispara. Ela precisa fazer duas coisas ao mesmo tempo: dizer **o que** a skill faz e listar **quais frases ou situações** devem dispará-la.

**Fórmula que funciona:**

1. Uma frase resumindo a função da skill
2. "Use quando/sempre que..." seguido de gatilhos concretos: verbos que o usuário usaria, sinônimos prováveis, nomes de arquivo ou extensão relevantes
3. Se a skill tem uma exceção clara (não usar para X, usar outra skill Y nesse caso), inclua isso também

**Erros comuns:**

- Description vaga demais ("ajuda com código") — dispara pouco ou dispara para tudo
- Description que só descreve o que a skill faz, sem listar gatilhos — o modelo não sabe quando ativar
- Gatilhos só em um idioma quando o uso real é bilíngue
- Duas skills com descriptions parecidas demais, competindo pelo mesmo disparo

## Processo de criação

1. **Defina o problema real.** Que tarefa recorrente essa skill resolve? Se não há repetição, talvez não precise virar skill.
2. **Liste os gatilhos reais.** Como as pessoas de fato pedem isso? Colete frases variadas, não só a mais óbvia.
3. **Escreva a description primeiro.** Antes do corpo do documento. Se a description não ficar clara, o resto não vai compensar.
4. **Escreva o processo como passos acionáveis**, não como teoria. Cada passo deve ser algo que dá para executar.
5. **Inclua exemplo real.** Abstração sem exemplo é a causa mais comum de skill mal aplicada.
6. **Teste o disparo.** Peça a tarefa de formas diferentes e veja se a skill ativa nos casos esperados e não ativa nos inesperados.

## Diretrizes

- Uma skill deve fazer uma coisa bem, não várias coisas de forma genérica.
- Se duas skills competem pelo mesmo gatilho, considere fundir ou diferenciar claramente o escopo de cada uma.
- Revise a description depois de usar a skill algumas vezes: gatilhos que pareciam óbvios no papel nem sempre são os que as pessoas usam na prática.

## Exemplo de description bem calibrada

```yaml
description: Especialista em impugnação de cálculos e laudos periciais trabalhistas.
  Use para: impugnar cálculos da parte contrária ou laudo do perito, extrair
  parâmetros da sentença, elaborar quesitos periciais, identificar erros de
  base de cálculo. Acione ao mencionar: impugnar cálculo, contestar planilha,
  crítica ao laudo, divergência de cálculo, quesitos ao perito.
```

Note a combinação: função clara + lista concreta de frases-gatilho que uma pessoa realmente usaria.
