---
name: adaptive-task-router
description: Automatically assess substantive tasks before execution to recommend the minimum sufficient ChatGPT surface, available model, and reasoning effort. Explicit text cues include ATR, ATR проверь, and ATR подбери. Use across domains for requests, revisions, analysis, research, files, tools, or repository work. Compare observable settings; stay silent when sufficient settings match.
---

# Adaptive Task Router

Recommend settings; never switch them, create tasks, delegate, or delay the user's work solely for routing. Explicit user preferences override these guidelines.

Treat standalone or leading commands `ATR`, `ATR проверь`, and `ATR подбери` as explicit routing requests, not incidental mentions in quoted material. Assess the accompanying task, or the active substantive task if no new task follows; ask what to assess if neither exists. These cues do not bypass host skill selection. The output gate still applies unless the user explicitly asks to see the recommendation.

## Short routing pass

Use the existing request and visible context. Do not call another model, browse, inspect files, or query tools solely to classify a task. No scores, exhaustive alternatives, or exposed chain of thought.

For a continuation with no new requirements, retain the active workflow's recommendation. Reassess new tasks, revisions, constraints, or changed runtime capabilities. Preserve unfinished work in the assessment.

Choose in order:

1. **Surface:** Chat for work achievable in conversation; Work for substantial dependent execution across materials/tools; Codex for actual repository development, tests, terminal, or git. Code alone does not imply Codex; difficulty alone does not imply Work. Consider accessible tools and local/cloud permissions.
2. **Model:** filter for reliable task fit before cost/speed. Use host metadata and relevant prior outcomes first. Smaller models fit clear transformations; balanced models fit bounded routine work; stronger models fit ambiguity or uncertain diagnosis; frontier models fit unusually difficult coupled reasoning. Downgrade only with clear grounds for sufficiency; don't offer a doubtful weaker candidate as equivalent. Sol with Medium can be preferable to Terra with more effort. Length or importance alone doesn't justify an upgrade. Do not assume plan access or cross-surface availability.
3. **Effort:** FAST for obvious local work; MEDIUM for several linked steps/checks; HIGH for nontrivial dependencies or diagnosis; VERY_HIGH for deeply interacting constraints/hypotheses; MAX rarely, when depth is the actual bottleneck. Map only to settings supported by the selected host/model. Speed, Pro, and Ultra are separate controls.

## Output gate

Read current settings only from host-supplied information or explicit user statements. A configured default or list of available models does not establish the active settings. Never guess.

- All three settings known and equal to the recommendation: no ATR message.
- A known setting differs: offer necessary changes once, including downgrades. Give up to three available options only if expected correctness, completeness and constraint compliance are comparable. Put the economical sufficient one first; exclude doubtful weaker options. One short line is preferred.
- Unknown settings: give tentative advice without inventing a previous value or claiming availability. Use a model class or conditional label if access is unknown.
- If the user continues without adopting advice, treat it as ignored and suppress repeated advice, including known mismatches. Within that workflow, reconsider unsolicited advice only after materially changed requirements and at least 30 minutes since the last advice, using reliable supplied timestamps. Time alone never triggers a reminder. If elapsed time is unknown, keep suppression; an explicit routing request or genuinely independent new task permits a fresh assessment. Do not query tools solely for timing.

Use the user's language and official UI labels. Continue the main task with current capabilities. If essential capabilities are absent, state the required transition briefly. A recommendation does not change the model executing this response.

## References — load only when needed

Use visible runtime metadata and previously verified mappings in context first.

- [surfaces.md](references/surfaces.md): surface capabilities or local/cloud distinctions.
- [models.md](references/models.md): model classes, availability, fallback.
- [reasoning.md](references/reasoning.md): supported labels and mapping.
- [routing-policy.md](references/routing-policy.md): ambiguous cases and message examples.
