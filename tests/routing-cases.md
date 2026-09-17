# Routing acceptance cases

These are cross-domain behavioral fixtures, not a benchmark or proof of quality. Test with the skill in a supported host; don't provide the expected answer to the evaluating model. `scripts/validate.py` checks fixture consistency, not the model's classification.

## Fixture conventions

Each fixture explicitly supplies its settings and available candidates; do not borrow the tester's actual model inventory. The inventories apply to the **target** surface/environment. Except where noted, the host has the required tools and every target surface is available.

Model classes: `economical` = Luna, `balanced` = Terra, `strong` = Sol, `frontier` = Astra, `legacy` = GPT-5.5, `specialist` = eligible Codex Spark. These representatives are test choices, not universal availability claims. `all` means the four current general-purpose classes are supplied. `unknown` means no inventory is supplied: recommend a capability class without claiming named-model access.

Current and expected tuples use `surface/model-class/effort-class`; `?` means unknown. `FAST` maps to the smallest useful supported option, not universally to Instant. Compare actual host labels and models in manual evaluation.

Flags: `normal` = no ignored-advice history; `repeat` = same ignored advice is already visible for the unchanged workflow; `show` = user explicitly requests the recommendation; `early-change` = materially changed requirements less than 30 minutes after ignored advice; `late-change` = materially changed requirements at least 30 minutes later; `no-time-change` = changed requirements but elapsed time is unknown after ignored advice. `continue` and `revision` without ignored advice follow the ordinary output gate. Known mismatches are also suppressed after ignored advice.

For all cases, assess the whole described task. One-line messages should name only needed changes, use the user's language, and never fabricate previous settings. Domain labels are examples, not routing rules.

| ID | Task and context | Current | Available | Expected surface | Expected model class | Expected reasoning | Message | Flag | Test rationale |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 01 | Correct two typos in a short sentence | Chat/economical/FAST | all | Chat | economical | FAST | no | normal | Obvious local edit; exact match |
| 02 | Translate a short literal everyday sentence | Chat/strong/HIGH | all | Chat | economical | FAST | yes | normal | Downgrade model and effort |
| 03 | Calculate 18 percent of 250 | Chat/frontier/MAX | all | Chat | economical | FAST | yes | normal | Simple arithmetic needs neither frontier nor Max |
| 04 | Compare three purchase options under a total budget and two constraints | Chat/balanced/FAST | all | Chat | balanced | MEDIUM | yes | normal | Several linked conditions and a check |
| 05 | Explain why the sky looks blue in plain language | Chat/economical/FAST | all | Chat | economical | FAST | no | normal | Familiar bounded explanation |
| 06 | Rewrite an email with the same meaning and a friendlier tone | Chat/economical/HIGH | all | Chat | economical | FAST | yes | normal | Only reasoning needs lowering |
| 07 | Summarize a provided one-page article in five bullets | Chat/economical/FAST | all | Chat | economical | FAST | no | normal | Direct bounded transformation |
| 08 | Resolve contradictions in a long policy document with exceptions across sections | Chat/balanced/MEDIUM | all | Chat | strong | HIGH | yes | normal | Deep bounded analysis can stay in Chat |
| 09 | Find the opening hours of one venue using a supported search tool | Chat/balanced/FAST | all | Chat | balanced | FAST | no | normal | One lookup is not automatically Work |
| 10 | Research competing technical claims across many sources and produce a verified report | Chat/strong/MEDIUM | all | Work | strong | HIGH | yes | normal | Dependent research and synthesis |
| 11 | Investigate an unfamiliar scientific controversy with conflicting evidence and tightly coupled hypotheses | Work/strong/HIGH | all | Work | frontier | VERY_HIGH | yes | normal | Stronger model and deeper hypothesis testing justified |
| 12 | Normalize the same header format across 50 uploaded text files and deliver the archive | Work/economical/FAST | all | Work | economical | FAST | no | normal | Bulk scope increases execution rather than depth |
| 13 | Extract names and dates from three short supplied documents into a small table | Chat/economical/FAST | all | Chat | economical | FAST | no | normal | Several files can still be bounded work |
| 14 | Reconcile several spreadsheets with ordinary joins and totals and deliver a checked workbook | Chat/balanced/MEDIUM | all | Work | balanced | MEDIUM | yes | normal | Multi-file artifact workflow |
| 15 | Design a polished substantial presentation from a long ambiguous brief and supplied brand assets | Work/balanced/MEDIUM | all | Work | strong | HIGH | yes | normal | Synthesis and professional artifact require judgment |
| 16 | Write a tiny standalone function that returns the larger of two integers | Codex/strong/HIGH | all | Chat | economical | FAST | yes | normal | Standalone code does not require a repository |
| 17 | Explain a pasted loop with four lines of straightforward code | Codex/balanced/MEDIUM | all | Chat | economical | FAST | yes | normal | Code explanation fits Chat |
| 18 | Diagnose a pasted off-by-one error and suggest a corrected snippet | Chat/balanced/FAST | all | Chat | balanced | MEDIUM | yes | normal | Small debugging needs linked checks |
| 19 | Fix an obvious one-file typo bug in this repository and run the existing test | Chat/balanced/MEDIUM | all | Codex | balanced | MEDIUM | yes | normal | Actual repository changes require Codex |
| 20 | Diagnose a nondeterministic repository race across services and implement a verified fix | Codex/strong/HIGH | all | Codex | frontier | VERY_HIGH | yes | normal | Coupled elusive root cause justifies escalation |
| 21 | Rename a well-scoped internal symbol across this repository and run tests | Codex/balanced/MEDIUM | all | Codex | balanced | MEDIUM | no | normal | Routine refactoring with exact match |
| 22 | Add focused regression tests for an existing well-understood parser bug | Codex/balanced/HIGH | all | Codex | balanced | MEDIUM | yes | normal | Routine test work can lower effort |
| 23 | Diagnose this CI failure caused by an evident missing build environment variable and patch configuration | Work/balanced/MEDIUM | all | Codex | balanced | MEDIUM | yes | normal | Project CI and configuration work fit Codex |
| 24 | Inspect this repository diff and prepare the explicitly requested commit | Chat/balanced/MEDIUM | all | Codex | balanced | MEDIUM | yes | normal | Actual git work needs repository workflow |
| 25 | Develop a repository migration across storage, auth and APIs with mutually interacting constraints | Codex/strong/HIGH | all | Codex | frontier | VERY_HIGH | yes | normal | Coupled architecture needs sustained reasoning |
| 26 | Critique a supplied system design with several ordinary tradeoffs; no files should change | Chat/balanced/MEDIUM | all | Chat | strong | HIGH | yes | normal | Architectural reasoning alone need not change surface |
| 27 | Analyze a difficult bounded mathematical proof with nonobvious but limited dependencies | Chat/strong/HIGH | all | Chat | strong | HIGH | no | normal | Scientific subject alone doesn't require frontier or Work |
| 28 | Resolve an exceptionally hard bounded proof with deeply coupled novel lemmas; depth is the established bottleneck | Chat/frontier/VERY_HIGH | all | Chat | frontier | MAX | yes | normal | Rare Max case with an explicit depth bottleneck |
| 29 | Extract the same two fields from 5000 records using a supplied schema and deliver checked files | Work/frontier/VERY_HIGH | all | Work | economical | FAST | yes | normal | Large repetitive data volume does not imply deep reasoning |
| 30 | Answer a new independent question about cooking rice after a completed Work report | Work/strong/HIGH | all | Chat | economical | FAST | yes | normal | Work to Chat for a separate simple task |
| 31 | Continue the unfinished distributed race fix from case 20 without new requirements | Codex/frontier/VERY_HIGH | all | Codex | frontier | VERY_HIGH | no | continue | Retain active workflow configuration |
| 32 | Revise the formerly routine refactor: preserve several conflicting public API and migration constraints | Codex/balanced/MEDIUM | all | Codex | strong | HIGH | yes | revision | New interacting constraints cause reassessment |
| 33 | Review a one-page summary; new clarification merely changes its requested tone | Chat/economical/FAST | all | Chat | economical | FAST | no | revision | Reassessment need not change settings |
| 34 | Correct two typos when none of the current settings are observable | ?/?/? | all | Chat | economical | FAST | yes | normal | Give recommendation without an invented previous value |
| 35 | Repeat case 34's unchanged workflow after identical tentative advice | ?/?/? | all | Chat | economical | FAST | no | repeat | Suppress repeated unknown-field advice |
| 36 | Correct two typos with current Chat and Luna known but effort unknown | Chat/economical/? | all | Chat | economical | FAST | yes | normal | Mention only unknown effort |
| 37 | Correct two typos with surface unknown but excessive model and effort known | ?/frontier/HIGH | all | Chat | economical | FAST | yes | normal | Show known downgrades and qualify unknown surface |
| 38 | Perform ordinary bounded analysis when only Terra is offered on the user's plan | Chat/balanced/MEDIUM | balanced | Chat | balanced | MEDIUM | no | normal | Respect actual inventory without a plan assumption |
| 39 | Solve a difficult bounded diagnostic task when Sol and Astra are unavailable and only GPT-5.5 is offered and sufficient | Chat/legacy/MEDIUM | legacy | Chat | legacy | HIGH | yes | normal | Select a genuinely sufficient available older alternative |
| 40 | Correct two typos with no observable current settings or model inventory | ?/?/? | unknown | Chat | economical | FAST | yes | normal | Class recommendation without a named entitlement claim |
| 41 | ATR provерь: correct two typos and explicitly show the configuration | Chat/economical/FAST | all | Chat | economical | FAST | yes | show | Explicit request to show overrides silence |
| 42 | ATR подбери without a new task during case 20's unfinished workflow | Codex/frontier/VERY_HIGH | all | Codex | frontier | VERY_HIGH | no | continue | Text cue targets the active substantive task |
| 43 | Repeat a simple edit while the host still reports Astra and High despite earlier ignored downgrade advice | Chat/frontier/HIGH | all | Chat | economical | FAST | no | repeat | Do not nag about an ignored known mismatch |
| 44 | Perform complex but bounded repository diagnosis in Codex cloud where Astra is absent and Sol is sufficient | Codex/balanced/MEDIUM | balanced,strong | Codex | strong | HIGH | yes | normal | Target environment availability overrides local Astra access |
| 45 | Do rapid text-only iteration on a small coding change when only eligible Spark is offered | Codex/specialist/FAST | specialist | Codex | specialist | FAST | no | normal | Specialized candidate only under supplied access |
| 46 | An urgent important but obvious spelling correction | Chat/strong/MAX | all | Chat | economical | FAST | yes | normal | Importance and urgency alone do not justify depth |
| 47 | Add coupled migration constraints two minutes after ignoring earlier refactor advice | Codex/balanced/MEDIUM | all | Codex | strong | HIGH | no | early-change | Reassess internally but avoid immediate repeated advice |
| 48 | Add genuinely interacting API constraints 30 minutes after ignoring earlier refactor advice | Codex/balanced/MEDIUM | all | Codex | strong | HIGH | yes | late-change | Materially changed needs at the cooldown boundary permit fresh advice |
| 49 | Return an hour later with no changed requirements after ignoring the simple-edit downgrade | Chat/frontier/HIGH | all | Chat | economical | FAST | no | repeat | Time alone is not a reminder trigger |
| 50 | Add coupled migration constraints after ignored advice with no trustworthy timestamps | Codex/balanced/MEDIUM | all | Codex | strong | HIGH | no | no-time-change | Never fabricate elapsed time to justify another suggestion |
| 51 | Explicitly request ATR and its configuration again immediately after ignoring a downgrade | Chat/frontier/HIGH | all | Chat | economical | FAST | yes | show | Explicit routing request can renew advice |
| 52 | Ask an independent research-and-report task after an ignored edit recommendation | Chat/strong/MEDIUM | all | Work | strong | HIGH | yes | normal | Independent task starts a new assessment |
| 53 | Thirty minutes later add a meaningful constraint but current settings already match its new requirements | Codex/strong/HIGH | all | Codex | strong | HIGH | no | late-change | Cooldown expiry does not override exact-match silence |
| 54 | Request familiar bounded analysis with Terra Sol and Astra supplied and relevant successful outcomes for all three; ask to see options | Chat/balanced/MEDIUM | balanced,strong,frontier | Chat | balanced | MEDIUM | yes | show | Show three actually sufficient configurations rather than padding uncertain options |
| 55 | Diagnose a bounded but ambiguous task where earlier equivalent Terra Medium attempts failed and Sol Medium succeeded | Chat/balanced/MEDIUM | all | Chat | strong | MEDIUM | yes | normal | Greater model capability is needed without automatically raising effort |
| 56 | Continue the same bounded ambiguous diagnosis on Sol Medium with relevant observed success | Chat/strong/MEDIUM | all | Chat | strong | MEDIUM | no | continue | Don't downgrade to Terra on price alone |

## Additional behavioral checks

- In a literal `ATR` or `ATR проверь` invocation with no accompanying or active substantive task, ask what task to assess. Do not classify the command itself as the user's substantive task.
- An incidental `ATR` in a quoted document is not an explicit routing command.
- If current settings are only saved defaults, treat active settings as unknown.
- If a user explicitly keeps a model/effort, respect that preference; do not keep arguing for a different configuration.
- When only `low` is offered by Astra, never recommend `none`. When only Light is offered, never invent Instant.
- If only weak models are available for a problem beyond their capabilities, qualify the fallback and state the gap. Do not claim reliable sufficiency.
- If a field changes from unknown to known and is mismatched, show the needed change.
- Keep computer/cloud permissions and missing tools separate from reasoning depth. If repository access is absent, recommend a supported transition without creating a new task or moving files.
- Ultra is a separate execution mode; it is not a sixth reasoning class and does not authorize subagents.
- The same task in another language should receive equivalent routing and a message in that language.
- In case 54, supply supported Medium for each candidate and a known cost ordering. Offer Terra Medium first and Sol Medium / Astra Medium as optional alternatives, without claiming all three are equally economical or required. If only one candidate fits, give only one.
- Cooldown checks use observed elapsed time after the last recommendation. At 29 minutes 59 seconds suppress; at 30 minutes with materially changed requirements reassess once. Do not query tools solely to manufacture timing data.
- If the user declines, continuation alone cannot reset suppression. An explicit routing request can, but it still doesn't imply permission to switch settings.
- Prior relevant failures can exclude Terra Medium from case 55's options; don't label it an equivalent alternative. If the failure was merely a missing input and that input is now provided, reconsider rather than permanently banning the model.
- Alternatives must be expected to satisfy the same correctness, completeness and constraint checks. If Terra produces materially worse results than Sol for the supplied task/context, exclude it even if it is cheaper. Comparable quality does not imply verbatim-identical output. Don't trial-run every candidate solely to route.
