# Changelog

## 0.1.4 — 2026-09-17

- Made pre-execution routing explicit for task answers and read-only tools, with independent model and effort checks.
- Clarified target-specific model/effort inventories and Codex priority for repository work; independent short Work requests can recommend Chat.
- Included simple requests in the discovery description; implicit selection remains a host decision, not a guaranteed interception.
- Sufficient settings remain silent without a grounded reason to change; typical examples do not impose mandatory configurations.
- Removed contradictory advice to display abstract reasoning levels when supported labels are unknown.

## 0.1.3 — 2026-09-17

- Made the new-conversation requirement prominent at the top of README: installation and updates are not automatically loaded into already open conversations.
- Existing Codex conversations keep Codex when it can do the work, including simple text requests; recommendations name concrete available models and supported effort instead of an abstract Chat fallback.
- Unknown active settings no longer hide a supplied model inventory; truly missing choices cause one short clarification. Shortened the checkpoint prompt and its quotable waiting instruction.

## 0.1.2 — 2026-09-17

- Shortened change proposals to settings and a brief switch-or-continue choice, without unsolicited task explanations or confirmation instructions.
- Mandatory host disclosures are kept in the same compact line instead of a separate paragraph; host requirements cannot be suppressed by the skill.

## 0.1.1 — 2026-09-17

- Configuration change proposals now explicitly recommend settings and pause before task execution until the user confirms switching or chooses to continue with current settings.
- Matching settings and suppressed advice keep executing without a checkpoint; explicit no-wait preferences are respected.
- Continuation is inferred from user intent, including ordinary assent and informal commands; no exact confirmation phrase is required, and assent does not imply switching models.
- Added conversation checks for the pause, resumption and option selection; removed an obsolete reference to a repository validator.

## 0.1.0 — 2026-09-17

- Initial portable skills-only plugin and repository marketplace for GitHub distribution.
- Surface → model → reasoning routing across task domains, including upgrades and downgrades.
- Runtime-first availability checks, honest handling of unknown settings, and concise output.
- Support for Luna, Terra, Sol, Astra and suitable alternatives supplied by the host.
- Continuation reuse, reassessment of revisions, and selective reference loading to reduce routing overhead.
- Short ATR text cues alongside native explicit invocation, ignored-advice suppression, a context-aware 30-minute cooldown, and up to three viable configuration options.
- Quality-first candidate filtering and relevant prior outcomes, including Sol Medium when Terra Medium is not demonstrably sufficient.
- Packaging checks and 56 routing fixtures; no executable scripts, runtime dependencies, automatic setting changes or external MCP server.
- Documented local installation versus workspace cloud import; account-wide personal availability and web/mobile testing remain unverified.
- GitHub installation instructions target the stable `main` branch; ongoing development remains on `dev`.
