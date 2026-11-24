# claude-praxinos-dev-plugin

A Claude Code plugin containing all shared Praxinos skills for development.

## Skills

| Skill | When it applies |
| --- | --- |
| `praxinos-agents` | Every task: token economy, line-ending preservation, no-log compilation, minimal command output. |
| `praxinos-development` | Creating or editing UE5 project, plugin, or engine code: Epic coding standard, member and include ordering, integration tests, compilation. |

## Install

In Claude Code:

```
/plugin marketplace add Praxinos/claude-praxinos-dev-plugin
/plugin install praxinos-dev@praxinos
```

Skills are then available as `praxinos-dev:praxinos-agents` and `praxinos-dev:praxinos-development`.

To pick up new versions: `/plugin marketplace update praxinos`.

## Add or change a skill

1. Create or edit `skills/<skill-name>/SKILL.md` (YAML frontmatter with `name` and `description`, then the instructions).
2. Bump `version` in `.claude-plugin/plugin.json`.
3. Run `claude plugin validate .` and open a pull request.
