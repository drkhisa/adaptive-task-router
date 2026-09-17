# Models and availability

Verified: 2026-09-17. This is a fallback snapshot, not an entitlement table. Prefer the model inventory and capabilities supplied by the target host. Do not browse solely to route every task.

## General-purpose candidates

| Class | Current candidate | Minimum sufficient use |
| --- | --- | --- |
| economical | GPT-5.6 Luna (`gpt-5.6-luna`) | Clear, bounded, repeatable extraction, transformation, classification, structured summaries |
| balanced | GPT-5.6 Terra (`gpt-5.6-terra`) | Familiar bounded reasoning, ordinary tool use, routine analysis and project work with clear checks |
| strong | GPT-5.6 Sol (`gpt-5.6-sol`) | Ambiguous, complex, open-ended work requiring deeper diagnosis, synthesis or polish |
| frontier | GPT-6 Astra (`gpt-6-astra`) | Hardest coupled end-to-end workflows across reasoning, code, research and tools |

These are task-fit classes, not proof of a universal price/speed ordering. Use actual host pricing/latency information when supplied. Evaluate all compatible models listed by the host, including new models, rather than treating this table as an allowlist.

Only optimize cost among candidates with a credible quality fit. If ordinary-looking work contains ambiguous diagnosis or a demonstrated failure by a balanced model, Sol may be the minimum sufficient choice at Medium. Prior observed success/failure informs similar tasks within the visible context; never fabricate benchmark results or confidence percentages.

GPT-5.5 (`gpt-5.5`) is a supported previous-generation alternative until its announced 2026-10-14 retirement from ChatGPT, Work and Codex with ChatGPT sign-in. It remains available in the API; API access does not establish ChatGPT access. Prefer current models when both are suitable, but support users whose available inventory includes only an older sufficient option.

GPT-5.3-Codex-Spark (`gpt-5.3-codex-spark`) is a text-only research preview for rapid coding iteration on eligible local clients/Pro accounts. Consider it only if the host supplies access and the coding task fits. It is not a universal substitute for Luna or a general Chat default.

Specialized models, third-party providers, or additional host models are candidates only when explicitly available and suitable for the task. Do not infer general availability from an API model catalog.

## Fallback

1. Filter by the target surface/environment, actual access, required modalities and tools.
2. Choose the least costly/fastest sufficient candidate from that inventory.
3. Distinguish unknown active settings from unknown inventory: the target host's explicit available-model metadata establishes candidates, even when its active model is not shown. Use actual names and supported levels. If no inventory is visible, consider a known current model only within its grounded supported choices; otherwise ask one short question for the missing model/effort choices. Do not present "fast model" or an unnamed capability class as actionable advice, and never claim an unverified entitlement.
4. If the inventory lacks a sufficient option, report the gap; use the strongest available option only as a qualified fallback.

Availability depends on plan, rollout, sign-in method, client and workspace controls. The current documentation lists Astra as unavailable in Codex cloud and Sol as available there; this restriction does not apply identically to local Codex. Free/Go/other plans must not receive an unconditional entitlement claim.

## Maintenance sources

- [Current model choices, class guidance, and client availability](https://learn.chatgpt.com/docs/models)
- [Workspace model availability](https://learn.chatgpt.com/docs/enterprise/workspace-model-availability)
- [API model catalog — API scope only](https://developers.openai.com/api/docs/models)

Update this file and `reasoning.md` together after an official product change; record a new verification date and adjust affected test fixtures. Do not update user configuration or infer retirement solely from a task's date.
