<p align="center">
  <img src="assets/banner.svg" alt="Claude Code Skills Starter Kit" width="100%"/>
</p>

<p align="center">
  <strong>A small, well-documented set of Claude Code skills</strong><br/>
  Install as-is · or use as a reference for building your own
</p>

<p align="center">
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-22c55e?style=flat-square&logo=opensourceinitiative&logoColor=white" alt="MIT license"/></a>
  <img src="https://img.shields.io/badge/skills-6-0ea5e9?style=flat-square" alt="6 skills"/>
  <img src="https://img.shields.io/badge/Claude_Code-skills-d97706?style=flat-square&logo=anthropic&logoColor=white" alt="Claude Code"/>
  <img src="https://img.shields.io/badge/idioma-pt--BR-009c3b?style=flat-square" alt="idioma pt-BR"/>
</p>

---

# Claude Code Skills Starter Kit

A small, well-documented set of Claude Code skills you can install as-is or use as a reference for building your own.

## What is a skill?

A skill is a folder containing a `SKILL.md` file that Claude Code reads to decide when and how to apply a specific workflow. The `description` field in the frontmatter is what triggers the skill: Claude matches the user's request against it to decide whether that skill is relevant.

## What's in this kit

Five general-purpose skills, each demonstrating a different design pattern:

| Skill | Pattern | What it does |
|---|---|---|
| `entrevistar` | Interactive elicitation | Interviews the user branch-by-branch to stress-test a plan before execution |
| `sintetizador` | Content distillation | Reduces any topic to its essential core, no filler |
| `commit-push-pr` | Confirmed workflow | Runs the git commit → push → PR flow with an explicit checkpoint at each step |
| `debug-sistematico` | Structured diagnosis | Reproduce → isolate → hypothesize → verify, before proposing any fix |
| `verificacao-antes-de-concluir` | Quality gate | Requires running and reading real verification output before declaring anything done |

Plus one meta-skill:

- **`criar-skill`** — teaches how to write a new skill from scratch, with a focus on writing a `description` that actually triggers correctly. Modeled after Anthropic's own skill-creator pattern.

The skill content is written in Brazilian Portuguese, since that's the language they were built and used in day to day. The structure and patterns translate directly to any language — use `criar-skill` as a template for writing your own in whatever language you work in.

## Installation

Copy the skill folders you want into your Claude Code skills directory:

```bash
git clone https://github.com/alexander-stack1/claude-code-skills-starter.git
cp -r claude-code-skills-starter/skills/entrevistar ~/.claude/skills/
cp -r claude-code-skills-starter/skills/sintetizador ~/.claude/skills/
# ...repeat for the ones you want
```

Adjust the target path to match your actual Claude Code skills directory.

## Writing your own

Start with `skills/criar-skill/SKILL.md`. It walks through the anatomy of a `SKILL.md` file, how to write a `description` that triggers reliably, and common mistakes to avoid.

The short version: write the `description` first. It's the only text used to decide whether your skill fires, so it needs to state clearly what the skill does and list the concrete phrases or situations that should trigger it.

## License

MIT. See [LICENSE](LICENSE).

## Author

Alexander Braz — [@oalexandrebraz](https://instagram.com/oalexandrebraz)
