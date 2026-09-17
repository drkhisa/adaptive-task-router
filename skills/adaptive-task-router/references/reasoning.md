# Reasoning classes and labels

Verified: 2026-09-17. Runtime-supported choices override this snapshot.

## Internal scale

| Class | Task property | Desktop / Work / IDE fallback label | CLI / API effort when supported |
| --- | --- | --- | --- |
| FAST | Obvious, local, few dependencies | Light | `none` for tasks requiring no reasoning if exposed; otherwise `low` |
| MEDIUM | Several linked steps and useful checks | Medium | `medium` |
| HIGH | Nontrivial diagnosis, dependencies or competing explanations | High | `high` |
| VERY_HIGH | Deeply interacting constraints or difficult hypothesis search | Extra High | `xhigh` |
| MAX | Exceptional problems where greater reasoning depth is the bottleneck | Max, only if exposed | `max`, only if exposed |

The FAST class deliberately groups the smallest useful settings; `none` and `low` are not semantically identical. Use the least setting that can handle the task and is actually offered. Map legacy `minimal` or other host labels only when their semantics are supplied; don't invent a universal conversion. If an intermediate class is absent, use the lowest supported option adequate for the task rather than fabricating a label.

## Model support

| Model | Official API support | Notes |
| --- | --- | --- |
| GPT-5.6 Sol | `none`, `low`, `medium`, `high`, `xhigh`, `max` | Default `medium` does not establish active effort |
| GPT-5.6 Terra | `none`, `low`, `medium`, `high`, `xhigh`, `max` | Client exposure may be narrower |
| GPT-5.6 Luna | `none`, `low`, `medium`, `high`, `xhigh`, `max` | Client exposure may be narrower |
| GPT-6 Astra | `low`, `medium`, `high`, `xhigh`, `max` | `none` is unsupported |
| GPT-5.5 | `none`, `low`, `medium`, `high`, `xhigh` | No API `max` in the current model documentation |
| Other models | Use their supplied supported list | API values do not prove that every client exposes them |

For Spark and additional models, use host metadata or the current model's documentation when explicit setup is requested. If exact settings are unavailable, recommend the internal depth in plain language and mark the precise UI setting as unknown.

`Instant` is not a universal alias for `none` or `low`. Preserve it only when a host explicitly supplies that label and its meaning. Use official labels of the actual client, not labels guessed from the product name.

## Separate controls

- **Fast mode / speed** affects processing latency and may cost more; it is not the FAST reasoning class. Don't recommend it as a way to save tokens.
- **Pro** reasoning mode is distinct from reasoning effort; don't automatically enable it.
- **Ultra** uses subagents. It is not the next reasoning level above Max, and ATR never authorizes delegation. If the current host exposes Ultra, report its separate execution mode when relevant and compare its underlying effort only when known.

## Sources

- [Models: Light, Low, High, Extra High, Max and Ultra](https://learn.chatgpt.com/docs/models#pick-a-reasoning-effort)
- [Reasoning effort and model-dependent support](https://developers.openai.com/api/docs/guides/reasoning#reasoning-effort)
- [GPT-5.6 Sol API support](https://developers.openai.com/api/docs/models/gpt-5.6-sol)
- [GPT-6 Astra API support](https://developers.openai.com/api/docs/models/gpt-6-astra)
- [GPT-5.6 Terra API support](https://developers.openai.com/api/docs/models/gpt-5.6-terra)
- [GPT-5.6 Luna API support](https://developers.openai.com/api/docs/models/gpt-5.6-luna)
- [GPT-5.5 API support](https://developers.openai.com/api/docs/models/gpt-5.5)
