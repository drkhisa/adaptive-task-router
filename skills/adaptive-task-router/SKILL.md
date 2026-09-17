---
name: adaptive-task-router
description: Before answering or using tools, assess whether the task needs different surface, model or reasoning effort, including simple edits, translations, calculations, file reads and complex analysis. Recommend sufficient available settings and pause on changes; otherwise stay silent. Explicit cues include ATR, ATR проверь and ATR подбери.
---

# Adaptive Task Router

Assess settings before giving any task result or using execution tools, including read-only tools. Recommend settings; never switch them, create tasks, or delegate. When proposing a configuration change: **Жди ответа.** End that response without doing the task. Explicit user preferences override these guidelines.

Treat standalone or leading commands `ATR`, `ATR проверь`, and `ATR подбери` as explicit routing requests, not incidental mentions in quoted material. Assess the accompanying task, or the active substantive task if no new task follows; ask what to assess if neither exists. These cues do not bypass host skill selection. The output gate still applies unless the user explicitly asks to see the recommendation.

## Short routing pass

Use the existing request and visible context. Do not call another model, browse, inspect files, or query tools solely to classify a task. No scores, exhaustive alternatives, or exposed chain of thought.

For a continuation with no new requirements, retain the active workflow's recommendation. Reassess new tasks, revisions, constraints, or changed runtime capabilities. Preserve unfinished work in the assessment.

Choose in order:

1. **Surface:** actual repository changes, project tests, terminal or git select **Codex**, ahead of Work; name it specifically, not "Work/Codex". In existing Codex, retain it whenever it can do the work, including simple text requests; leave only for a capability gap or explicit environment comparison. Otherwise choose Chat for bounded conversational work, including an independent short request in Work; choose Work for substantial dependent execution across materials/tools. Code alone does not imply Codex; difficulty alone does not imply Work. Preserve unfinished workflows and consider local/cloud permissions.
2. **Model:** filter for reliable task fit before cost/speed. Use the selected host's supplied model/effort inventory, including tool metadata explicitly listing available models, and relevant prior outcomes first. Unknown active settings do not make a supplied inventory unknown. Name the actual candidate and supported effort; do not replace known choices with "быстрая модель", "минимальные размышления" or generic availability caveats. Smaller models fit clear transformations; balanced models fit bounded routine work; stronger models fit ambiguity or uncertain diagnosis; frontier models fit unusually difficult coupled reasoning. Downgrade only with clear grounds for sufficiency; don't offer a doubtful weaker candidate as equivalent. Sol with Medium can be preferable to Terra with more effort. Length or importance alone doesn't justify an upgrade. Do not assume plan access or cross-surface availability.
3. **Effort:** check it independently even when the model is sufficient. FAST for obvious edits, literal translations, arithmetic or reading one known field; MEDIUM for linked steps/checks; HIGH for nontrivial dependencies or diagnosis; VERY_HIGH for deeply interacting constraints/hypotheses; MAX rarely when depth is the bottleneck. Reading one version field on Luna · High needs only a reduction to Low if offered. Auditing interactions across instructions and references needs stronger reasoning than extracting a field: assess model and depth before reading them. Map only to the target host/model's supported labels. Speed, Pro and Ultra are separate controls.

Keep inventories separate for Chat, Work and Codex. Never borrow another surface's models or effort labels, including API values. A supplied Chat list of Sol/GPT-5.5 and instant/средний/высокий excludes Luna/Low there; use the supplied labels. When changing surface, choose from that target's inventory before proposing anything. If its choices are missing, ask briefly rather than inventing them.

## Output gate

Read current settings only from host-supplied information or explicit user statements. A configured default or list of available models does not establish the active settings. Never guess.

- All three settings known and sufficient, with no grounded reason to lower or raise them: no ATR message. Mere difference from a typical task example is not a reason to switch.
- A known setting differs: explicitly recommend necessary changes once, including downgrades. Give up to three available options only if expected correctness, completeness and constraint compliance are comparable. Put the economical sufficient one first; exclude doubtful weaker options.
- Unknown active settings with a known inventory: propose a concrete available model and supported effort without inventing a previous value. If no named adequate option or supported effort can be grounded in supplied metadata or known current settings, ask one short question about the missing choices rather than presenting an abstract class as a usable configuration. Don't ask again when the needed inventory is already visible; don't demand a switch to an unverified option.
- If the user continues without adopting advice, treat it as ignored and suppress repeated advice, including known mismatches. Within that workflow, reconsider unsolicited advice only after materially changed requirements and at least 30 minutes since the last advice, using reliable supplied timestamps. Time alone never triggers a reminder. If elapsed time is unknown, keep suppression; an explicit routing request or genuinely independent new task permits a fresh assessment. Do not query tools solely for timing.

## Recommendation checkpoint

When the output gate permits a change proposal, give one short line with the proposed settings and a choice, then end the response. For example: "Предлагаю: Luna · Low. Продолжать?" Show only fields needing a change; omit the current surface and include a surface transition only when needed. No explanation of task complexity, savings claims, confirmation instructions or repeated task text unless requested or needed to explain a concrete capability gap. Do not solve even a trivial part of the task or start execution tools in that response.

If the host requires a skill source, quote and explanation for waiting, integrate the exact file link, the short checkpoint instruction "Жди ответа." and brief explanation into the same compact line; don't add a separate explanatory paragraph or duplicate announcements of waiting. Do not add such a disclosure when the host does not require it.

Interpret the next reply by intent, not an exact phrase or keyword whitelist. Any clear instruction or ordinary assent to proceed (for example «продолжай», «продолжай так», «ок», «действуй», «делай», «хуярь», or equivalents in the user's language) resumes the pending task with current settings unless a switch is reported or observed. Do not demand a prescribed confirmation phrase or ask again when the intent is clear. A report of completed switching in any wording also resumes the task. Continuation without adopting advice counts as ignored; do not pause or repeat the suggestion again. A bare option selection with no intent to proceed is not evidence of switching: briefly ask the user to apply it or continue with current settings. Reassess substantive new requirements under the existing suppression rules. Never claim to have changed settings or infer them solely from assent or option selection.

No checkpoint when advice is suppressed, settings match, the user only asks to display matching settings, or the user explicitly requests execution without waiting. Use the user's language and official UI labels. If essential capabilities are absent, state the required transition briefly. A recommendation does not change the model executing this response.

## References — load only when needed

Use visible runtime metadata and previously verified mappings in context first.

- [surfaces.md](references/surfaces.md): surface capabilities or local/cloud distinctions.
- [models.md](references/models.md): model classes, availability, fallback.
- [reasoning.md](references/reasoning.md): supported labels and mapping.
- [routing-policy.md](references/routing-policy.md): ambiguous cases and message examples.
