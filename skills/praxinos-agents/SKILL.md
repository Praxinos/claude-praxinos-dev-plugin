---
name: praxinos-agents
description: General working rules for any agent. Apply to every task.
---

# Praxinos Agents

Use as few tokens and as little quota as possible without affecting the final result.

Preserve the line-ending format (LF or CRLF) required by the repository's Git configuration when editing files.

For any compilation, redirect the command output to null to enforce a no-log compilation.
If the no-log compilation failed, compile again normally to retrieve errors.

For any command execution, limit its output as much as possible to retrieve only the needed parts.
