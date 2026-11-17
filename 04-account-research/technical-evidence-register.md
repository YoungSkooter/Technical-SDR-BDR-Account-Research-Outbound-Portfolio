# Technical Evidence Register: Ramp

## Purpose

Keep public evidence separate from interpretation. This register is a working research artifact; verify links, publication dates, and exact wording before using claims in prospect-facing material.

| Evidence area | What the research looked for | Status | How it informs the hypothesis |
|---|---|---|---|
| Ramp Stack product context | Public product material describing accounting automation | Publicly described; revalidate current page | Suggests multi-step financial workflow relevance |
| Accounting workflow steps | Reconciliation, depreciation/amortization, journal-entry workflows and accounting integrations | Publicly described in the research exercise; confirm exact scope | Indicates potential external system and state-transition boundaries |
| Engineering / agent workflow material | Public engineering discussion of agent loops, memory, or human-in-the-loop pauses | Publicly described in the research exercise; confirm source and date | Suggests a useful discovery topic around long-running execution |
| Internal orchestration architecture | Whether Ramp uses Restate, Temporal, queues, a custom runtime, or another system | Unknown | Must not be asserted |
| API timeout or duplicate-write incidents | Whether any such incidents have occurred | Unknown | Discovery hypothesis only |
| Idempotency strategy | How external accounting writes are protected | Unknown | High-value technical discovery question |
| Scale and concurrency | Workflow volume, throughput, concurrency, rate limits | Unknown | Do not invent numbers or bottlenecks |

## Evidence classification

### Verified public context
Use only statements that can be directly supported by current public pages or official company material.

### Reasonable inference
Accounting automation commonly involves stateful, multi-step workflows and external system integrations. That makes durable execution a relevant topic to investigate.

### Hypotheses
- A workflow may pause for human approval.
- A worker may restart during a multi-step process.
- An external API may commit a write while the caller loses the response.
- Teams may need idempotency or reconciliation to protect side effects.

### Unknowns to validate
- Current workflow orchestration technology.
- Existing retry and recovery design.
- Whether any workflow creates meaningful operational toil.
- Whether the team is evaluating alternatives.
- Which engineering team owns the relevant workflow.

## Source register

Use primary sources first:
- Ramp product and company pages: https://ramp.com/
- Ramp engineering / developer content: https://ramp.com/blog (confirm the exact relevant article)
- Restate product documentation: https://docs.restate.dev/
- Restate use cases: https://restate.dev/use-cases

Do not treat this source list as proof of a particular Ramp implementation. Add exact article titles, URLs, dates, and quoted supporting passages when conducting a refreshed account-research pass.
