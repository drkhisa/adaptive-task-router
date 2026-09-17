# Surfaces and capabilities

Verified: 2026-09-17. Runtime information takes precedence over this snapshot.

| Surface | Choose for | Do not infer from |
| --- | --- | --- |
| Chat | Dialogue, explanations, editing, small calculations, bounded analysis, small file tasks achievable in the conversation | A task being simple enough to avoid all tools |
| Work | Substantial dependent execution from materials to a finished result: research, multiple files/apps, data pipelines, professional artifacts | Difficulty alone, one file, or a long answer |
| Codex | Actual work on a software repository: changes, project debugging, tests, builds/CI, terminal, git, commits or PR preparation | Any code snippet, explanation, or programming topic |

Repository development takes priority over Work. A bounded explanation of code usually fits Chat even if it requires careful reasoning.

## Environment matters

ChatGPT desktop offers Chat and Work; Codex is another product workflow. Work Cloud runs in an isolated environment and cannot directly access local device files, apps, or browser tabs. Uploaded files, authorized connections, local desktop permissions, and repository access affect feasibility.

Recommendations are about workflows, not permission grants. Don't imply a switch will automatically transfer files, preserve every tool, grant access, or start execution. When proposing a change, follow the recommendation checkpoint in `SKILL.md`: wait for the user's decision before execution. If it lacks essential capabilities, explain the gap.

Model access can differ between local Codex and Codex cloud. Resolve model choices for the recommended execution environment rather than borrowing the current host's list unconditionally.

## Sources

- [ChatGPT desktop app](https://learn.chatgpt.com/docs/app)
- [ChatGPT Work overview](https://learn.chatgpt.com/docs/enterprise/chatgpt-work-overview)
- [Models and client availability](https://learn.chatgpt.com/docs/models)
