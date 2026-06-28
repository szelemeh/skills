# skills

My own agent skills. Small, composable, and model-agnostic, designed to be easy to
adapt and to work with any coding agent. Hack on them and make them your own.

## Install

```bash
npx skills@latest add szelemeh/skills
```

Pick the skills you want and which agents to install them on.

## Skills

| Skill | What it does |
| --- | --- |
| [`self-improve`](./skills/self-improve/SKILL.md) | Reflect on the session, find where things stumbled or you got corrected, and propose small surgical fixes to the setup. |

## Layout

```
skills/<name>/
└── SKILL.md        # frontmatter (name, description) + the instructions
```
