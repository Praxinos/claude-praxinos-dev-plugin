# claude-praxinos-dev-plugin

A Claude Code plugin containing all shared Praxinos skills for development.

## Skills

| Skill | When it applies |
| --- | --- |
| `praxinos-development` | Creating or editing UE5 project, plugin, or engine code: Epic coding standard, line endings, no-log compilation, member and include ordering, integration tests, compilation. |

## Install

In Claude Code:

```
/plugin marketplace add Praxinos/claude-praxinos-dev-plugin
/plugin install praxinos-dev@praxinos
```

The skill is then available as `praxinos-dev:praxinos-development`.

To pick up new versions: `/plugin marketplace update praxinos`.

## Add or change a skill

1. Create or edit `skills/<skill-name>/SKILL.md` (YAML frontmatter with `name` and `description`, then the instructions).
2. Bump `version` in `.claude-plugin/plugin.json`.
3. Run `claude plugin validate .` and open a pull request.
