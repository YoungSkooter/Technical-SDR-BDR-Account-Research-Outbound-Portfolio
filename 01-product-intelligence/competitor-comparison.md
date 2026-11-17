# Competitor and Alternative Framing

## The real competitive set

A prospect may compare Restate with:
- Temporal and other workflow orchestration platforms.
- Cloud-native workflow services such as AWS Step Functions.
- Queues and task systems combined with application-managed state.
- Existing agent frameworks and checkpointing features.
- Internal workflow engines and custom orchestration code.

The prospect's current approach may be entirely adequate. The goal is to understand its workload and constraints, not to force a replacement conversation.

## Restate vs. Temporal: balanced discussion

Both products address durable workflow execution. Avoid simplistic claims that one is reliable and the other is not.

Useful dimensions to explore:
- Programming model and developer ergonomics.
- Workflow and state modeling requirements.
- Deployment and operational ownership.
- Language/runtime requirements.
- Throughput and concurrency patterns.
- Existing team expertise and ecosystem.
- Migration effort and the specific workload being considered.

Temporal workflows use deterministic workflow code and Activities for external side effects. Temporal's architecture and deployment requirements vary by deployment model; do not claim every Temporal deployment requires Cassandra or Redis.

Restate's approach and deployment model have their own trade-offs. Do not claim that a single binary means zero operational work or that it is automatically a drop-in replacement for Temporal.

## Restate vs. cloud-native workflow services

Managed cloud workflow services may be attractive when a team already operates primarily in one cloud ecosystem and values managed infrastructure.

Explore:
- Whether the workflow model fits the application's code and runtime.
- Vendor and cloud coupling considerations.
- Developer workflow and local testing.
- Operational ownership.
- Pricing at the prospect's workload scale.
- Integration with existing services.

## Restate vs. queues plus custom code

Queues are useful and often necessary. The question is not whether queues are bad; it is whether the application has accumulated substantial custom code for durable state, timers, retries, and recovery.

Ask:
- Which component owns workflow state?
- How are delayed steps represented?
- How are duplicate deliveries handled?
- How does the team recover a partially completed workflow?
- How much custom infrastructure must the team maintain?

## Objection-handling principle

Validate the current solution first. Ask what works, where it becomes difficult, and whether a specific workload creates a gap. Recommend a comparison only when a concrete problem has been established.
