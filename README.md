# skills

My own agent skills. Small, composable, and model-agnostic. Each skill lives in
its own directory under [`skills/`](./skills) with a `SKILL.md` that the agent
loads on demand.

## Install

These skills are model-agnostic (Claude Code, OpenCode, etc.).

### With the skills CLI

```bash
npx skills@latest add szelemeh/skills
```

Pick the skills and which agents to install them on. This reads
[`.claude-plugin/plugin.json`](./.claude-plugin/plugin.json) for what's available.
The repo is private, so you need git access to it (SSH key or `gh auth login`).

### Manually

A skill is just a folder with a `SKILL.md`. Copy it where your agent looks for
skills. For Claude Code in every repo (user-level):

```bash
tmp=$(mktemp -d) && git clone --depth 1 https://github.com/szelemeh/skills.git "$tmp" \
  && mkdir -p ~/.claude/skills && cp -R "$tmp"/skills/self-improve ~/.claude/skills/ \
  && rm -rf "$tmp"
```

For a single repo instead, copy the skill folder into that repo's `.claude/skills/`.

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
