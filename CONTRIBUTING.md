# Contributing

This is a small, opinionated collection of Claude Code skills. Contributions are welcome, especially new skills that demonstrate a pattern not already covered here.

## Adding a new skill

1. Create a new folder under `skills/` named after your skill.
2. Add a `SKILL.md` file following the structure described in `skills/criar-skill/SKILL.md`: frontmatter with `name` and `description`, then `Propósito`, `Quando usar`, `Processo`, `Diretrizes`, and at least one concrete example.
3. Spend the most effort on the `description` field. It is the only text Claude uses to decide whether the skill fires, so it needs to state what the skill does and list the concrete phrases or situations that should trigger it.
4. Open a pull request. Explain what problem the skill solves and why it is not already covered by an existing one.

## Improving an existing skill

If a skill's trigger phrases are missing an obvious case, or a step in its process is unclear, open a pull request with the specific change and the reasoning behind it.

## Language

Skill content lives in Brazilian Portuguese, since that is the language these skills were built and used in day to day. Keep new skills in Portuguese unless you are contributing a translated variant explicitly, in which case name the folder accordingly (for example `nome-da-skill-en`).

## Pull requests

Keep pull requests scoped to one skill or one fix at a time. Small, reviewable changes get merged faster than large batches.
