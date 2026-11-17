# Technical Decision-Maker Outreach

## Target persona

Staff / Principal Engineer, Platform Engineering Lead, or Engineering Manager responsible for workflow architecture.

## Email option

**Subject:** Durable execution for multi-step workflows

Hi {{FirstName}},

I noticed Ramp's public focus on accounting automation and workflows that can involve reconciliation, review, and downstream system updates.

For teams building these processes, a design question often emerges: where does durable workflow state live, and how does the application recover when a process is interrupted between steps?

Restate is one approach to durable execution. It provides primitives for recording workflow progress and coordinating long-running work. External side effects still need application-level idempotency or reconciliation, so I'm particularly interested in how teams draw that boundary.

Is workflow orchestration owned by your platform team, or is it implemented within the product services?

Best,  
{{YourName}}

## Short LinkedIn message

Hi {{FirstName}} — I'm researching how engineering teams manage durable state, retries, and external side effects in long-running workflows. Given Ramp's public accounting automation work, I was curious whether workflow orchestration is owned centrally by platform engineering or within individual product teams.

## Why this angle

A senior technical evaluator is more likely to care about:
- Ownership boundaries.
- State and recovery semantics.
- Deployment and operational trade-offs.
- Integration with existing architecture.
- Whether a dedicated runtime solves a specific workload gap.

## Do not assume

- Ramp uses Postgres, Redis, Kafka, Temporal, or a custom runtime for this workflow.
- The team has concurrency bottlenecks.
- The product processes thousands of jobs.
- The team has suffered duplicate journal entries.
- Restate is automatically a replacement for the current platform.
