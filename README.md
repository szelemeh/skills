# skills

My own agent skills. Small, composable, and model-agnostic. Each skill lives in
its own directory under [`skills/`](./skills) with a `SKILL.md` that the agent
loads on demand.

## Skills

| Skill | What it does |
| --- | --- |
| [`self-improve`](./skills/self-improve/SKILL.md) | Reflect on the interaction, find where things stumbled, and propose small surgical changes to the setup that generalize. |

## Layout

```
skills/<name>/
└── SKILL.md        # frontmatter (name, description) + the instructions
```

## Releases

Versioning and changelogs are automated with
[release-please](https://github.com/googleapis/release-please). Each skill is a
separate component (e.g. tag `self-improve-v0.1.0`), driven by
[Conventional Commits](https://www.conventionalcommits.org/): use `feat:`,
`fix:`, `docs:` etc. Merging the release-please PR cuts the release.
