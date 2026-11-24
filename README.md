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

## Companion plugins

Epic plugins that complement `praxinos-dev`. The code-style plugins also enforce rules that `praxinos-development` relies on (Epic coding standard details, hoisted container types, doc comments on every declaration).

### Code style

| Plugin | Purpose | Examples |
| --- | --- | --- |
| `code-style-core` | Language-neutral rules: one responsibility per class, every function documented, one call per line. Provides the review commands. | `/review-pass`, `/style-pass Source/MyModule`, `/architecture-pass` |
| `code-style-cpp` | C++ form of those rules (Allman braces, `nullptr`, explicit lambda return types) and a linter run on every edited file. | Automatic on every `.h` or `.cpp` edit |
| `code-style-cpp-unreal` | Unreal-specific rules: `UE_LOGF_FUNC`, `TConstArrayView`, `FStringView`, `Super` call order, `TObjectPtr`. | Automatic on Unreal C++ code |

### Git and pull requests

| Plugin | Purpose | Examples |
| --- | --- | --- |
| `conventional-commits-helper` | Generates and validates commit messages, PR titles and descriptions in Epic's conventional format. | "commit my changes", "create a PR", "validate PR format" |

### Unreal Engine

| Plugin | Purpose | Examples |
| --- | --- | --- |
| `ecabridge` | Drives the open Unreal Editor: actors, Blueprints, widgets, materials, Niagara. The editor must be running. | "Create a PointLight above the player" |
| `ue-asset-tools` | Inspects and modifies `.uasset` files without opening the editor: references, properties, duplication, deletion. | "What references M_Base?", "Set bCastShadow to false on all SM_Rock_*" |
| `ue-deprecate-code` | Guide for deprecating UE code: `UE_DEPRECATED`, CoreRedirects, two-version retention rule. | "Rename this UPROPERTY and keep compatibility" |
| `ue-python-api` | Searches classes and methods in Unreal's Python API. | "How do I list the assets in a folder in Python?" |
| `ue-utrace-tools` | Analyzes `.utrace` performance traces: hitches, memory, network, comparisons, reports. | "Analyze this trace, what's slow?", "Compare these two traces" |
| `slate-widget-toolkit` | Creates, modifies, tests and converts (UMG to Slate) editor Slate widgets. | "Add a toolbar button that opens our settings", "Convert WBP_Toolbar to Slate" |
| `eca-code-analyzer-documenter` | Analyzes a UE C++ class (methods, properties, features) and generates its documentation. | "Document UMyComponent" |
| `epic-developer-assistant` | Asks Epic's developer assistant about Unreal, Verse and UEFN. | "How does RPC replication work?" |

### Productivity and cost

| Plugin | Purpose | Examples |
| --- | --- | --- |
| `ai-cost-advisor` | Audits Claude usage and recommends savings. | `/cost-audit` |
| `skill-starter-pack` | Epic-standard writing, expert briefings, session handoffs, inbox triage, Google Docs editing. | "Brief me on Nanite", "handoff" |
| `personal-assistant-setup` | Sets Claude up as a personal assistant: projects, work journal, sourced research. | "Research X", "new work item" |

## Add or change a skill

1. Create or edit `skills/<skill-name>/SKILL.md` (YAML frontmatter with `name` and `description`, then the instructions).
2. Bump `version` in `.claude-plugin/plugin.json`.
3. Run `claude plugin validate .` and open a pull request.
