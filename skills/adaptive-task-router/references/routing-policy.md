# Routing policy

This reference clarifies the short pass in `SKILL.md`; do not load it for obvious tasks. It contains policy, not a model catalog.

## Minimum sufficient

Evaluate the requested outcome and unresolved work, rather than topic, length, job title, or prestige. Prefer cheaper/faster sufficient configurations, accounting for uncertainty, dependent steps, verification, required tools, and consequences of an error.

High consequences primarily increase the need for trustworthy sources and checks. They do not automatically imply a stronger model or higher effort. Repetitive bulk processing primarily increases execution scope. It does not automatically increase reasoning depth.

Do not raise both model and effort by habit. Select model capability first, then the smallest useful effort within that model. Tool access is a host capability: more reasoning cannot supply missing tools, permissions, or files.

Quality is a feasibility filter before economy, not another reason to choose the cheapest default. Balanced models suit familiar bounded work with clear success criteria. Ambiguous diagnosis, unfamiliar mechanisms or uncertain adequacy call for a stronger model even when the needed effort is only Medium. If a cheaper model's sufficiency is doubtful and the current stronger configuration is adequate, preserve it rather than forcing a downgrade.

Use observed outcomes of relevant earlier attempts in the visible conversation: if Terra failed this type of task and Sol succeeded, do not propose Terra again without a concrete reason the new task is easier or the failure is addressed. Do not generalize one failure into a permanent ban. More effort is not guaranteed to replace greater model capability. A missing source, tool or input is not evidence that a stronger model is needed.

Escalate for genuinely difficult synthesis, ambiguity, interacting constraints, or early mistakes that compound through later reasoning. Lower the recommendation again for a new, simpler task. Retain the explicit preferences of a user who knowingly chooses another configuration.

## Conversation scope

"Continue" inherits the unfinished workflow. A clarification or correction causes a fresh brief assessment of the workflow with that information included; reassessment need not cause a setting change. A clearly independent request is assessed on its own.

Do not recommend leaving an existing Codex conversation just because a command or standalone question is easy. Keep Codex if it can execute the request and recommend its concrete model/effort instead. Leaving Codex requires a concrete capability gap or an explicit environment comparison request. In ChatGPT, independent tasks may still justify switching between Chat and Work. Recommend a transition without moving the conversation or creating another task yourself.

## Availability and observability

Treat current surface, active model, effort, and available alternatives as separate fields. Each can be unknown. Tool schemas can establish supported alternatives when explicitly described as available to this host; they do not necessarily identify the active model. User-reported settings can be used as reported, with subsequent corrections taking precedence.

An unavailable preferred model requires a sufficient available alternative. If none is adequate, explain the capability gap briefly; do not pretend an available weak model will reliably solve the problem. Use concrete names and supported levels from the target host's supplied inventory even when active settings are unknown. Only if grounded choices cannot be established, ask briefly for missing models or levels. Don't ask for a plan or model inventory on every turn.

Unknown current fields cannot be compared. Known matching fields should not be repeated. Never assume the user adopted advice, but do not keep repeating it either. When all fields are known and match the minimum sufficient recommendation, stay completely silent unless asked to show it.

## Ignored advice and timing

Keep a small state in visible conversation context: the active task, last advice and options, whether the user accepted/declined/continued without adopting it, and a timestamp only if supplied. Do not create state files or timers. If earlier state is no longer visible, do not invent it.

Continuing the work without accepting or implementing the suggestion counts as ignoring it. An explicit refusal also suppresses repetitions. Reassess revisions internally without assuming permission to send another configuration message.

For unsolicited advice in the same workflow, require both a material change in the needed configuration and a reliably observed interval of at least 30 minutes after the last advice. Short corrections, added wording and minor details do not qualify. At 30 minutes, a new constraint that introduces deeper dependencies or required tools can justify one fresh recommendation. Waiting alone cannot.

If the interval is unknown, keep the ignored-advice suppression for that workflow. Do not call a clock tool solely to implement this policy: a current timestamp alone cannot reconstruct a missing earlier timestamp. A fresh explicit routing request permits advice again; a genuinely independent new task starts a new assessment. The normal exact-match silence rule still applies unless the user asks to see the result.

Missing essential capabilities must be explained as part of completing the main task, even during the cooldown. This is a concrete execution limitation, not another unsolicited model suggestion. Don't claim that work was performed when the tools were absent.

## Proposal before execution

A change recommendation is a checkpoint, not an aside attached to an already completed task. Propose only needed settings and ask briefly whether to switch or continue, then stop. Default to one short line without reasoning, savings claims or instructions about how to confirm. Give an explanation only on request or for a concrete capability gap. Required host disclosures follow the compact format in `SKILL.md`; no extra paragraph. Do not append the answer, corrected text or execution results. Keep the pending task in visible context for the next reply.

Understand the reply semantically: a report of switching in any wording resumes the task, and any clear go-ahead or ordinary assent resumes with current settings unless a switch is reported or observed. "продолжай", "продолжай так", "ок", "действуй", "делай", "хуярь" and equivalents are examples, not an exhaustive list or mandatory phrases. Do not demand exact wording or another confirmation once the intent is clear. Assent alone does not establish switching. An explicit refusal or continuation without adopting advice suppresses repeated advice. Selecting an option without a go-ahead does not establish active settings; selecting an option together with a go-ahead permits execution on observable current settings without another confirmation. Merely displaying a matching configuration creates no checkpoint. Explicit requests to execute without waiting take precedence.

## Several viable options

Offer one to three configurations only when each is available and expected to produce comparable task quality: correctness, completeness, compliance with constraints and required checks. Use the same success criteria for every option. Comparable quality does not mean identical wording. Rank the economical sufficient option first, then at most two alternatives. Do not enumerate the inventory or pad to three. Exclude cheaper configurations with doubtful quality or likely extra failed attempts. Do not run each candidate merely to test routing.

If a user wants the current sufficient stronger model, it can remain an option. Compare supported effort within each candidate rather than mechanically assigning the same effort to every model. Describe cost/speed differences only when grounded in host information or the maintained documentation for that host; don't transfer API prices to ChatGPT credits.

Example, with all options and the cost ordering supplied by the host:

> Предлагаю: Terra · Medium / Sol · Medium / Astra · Medium. Продолжать?

## One-line examples

Examples use the compact checkpoint format; stop before doing the task. Availability remains a condition for named options.

Only effort changes:

> Предлагаю: Light. Продолжать?

Only model changes:

> Предлагаю: Luna. Продолжать?

Several known fields change:

> Предлагаю: Work · Astra · High. Продолжать?

Only one field is unknown:

> Предлагаю: Light. Продолжать?

All settings and model access unknown:

> Какие модели и уровни доступны?

Essential repository tools absent:

> ⚙️ Для правки репозитория нужен Codex с доступом к проекту; здесь могу разобрать ошибку по предоставленному коду.

Never write an old value unless it is known. Use the host's actual labels; these examples assume that their named options are available. "Minimum sufficient" is a reasoned recommendation, not a measured guarantee of quality or token savings.
