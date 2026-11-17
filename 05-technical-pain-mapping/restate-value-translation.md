# Translating the Technical Scenario into Restate Value

## The technical problem is not simply "retries"

Retries are only one part of reliable workflow execution. A production workflow may also need:
- Durable progress.
- Delayed execution and timers.
- Human-in-the-loop pauses.
- Coordination around stateful entities.
- Explicit handling of external side effects.
- Recovery after process interruptions.

A queue can deliver work, but the application may still need to manage the broader workflow lifecycle.

## Value mapping

| Prospect challenge to validate | Restate-related capability | Careful value statement |
|---|---|---|
| Workflow state is spread across services | Durable execution model | May simplify how progress is represented and recovered |
| Completed steps are repeated after interruption | Recorded durable step results | Can resume from recorded progress when implemented with durable primitives |
| Process must wait for approval | Durable waiting / timers | Can support long-running pause-and-resume workflows |
| Per-entity state needs coordination | Virtual Objects | May provide a clearer model for keyed state and coordinated access |
| Workload needs throughput control | Flow control | Can help manage configured concurrency and throughput |
| Team maintains custom orchestration | Runtime primitives | May reduce custom infrastructure the team needs to build and maintain |

## What Restate does not remove

- Business logic.
- Application-level validation.
- External system availability.
- External API idempotency requirements.
- Security and authorization.
- Observability and operational ownership.
- The need to test failure modes.
- The need to choose suitable retry and concurrency policies.

## Business-value discovery

Do not claim a specific percentage reduction in engineering time or LLM spend without evidence. Ask:
- How many engineering cycles go into maintaining workflow infrastructure?
- How often do operators manually recover stuck processes?
- What is the cost of repeating an expensive step?
- Which workflow failures affect customer trust or financial correctness?
- Is the current approach limiting the launch or expansion of automation?

## Concise positioning

"Restate gives developers primitives for durable execution, so long-running workflows can preserve progress and recover more predictably. The opportunity is to reduce the amount of custom state, retry, and coordination machinery the team has to maintain—while still handling external side effects safely in the application."
