# Technical Capabilities: Restate

This document summarizes the technical concepts relevant to an SDR conversation. It is not a substitute for the current product documentation.

## Durable execution

Durable execution is a programming and runtime approach in which workflow progress is persisted. When execution is interrupted, the workflow can resume from recorded progress rather than starting over indiscriminately.

A developer must structure the workflow using the product's durable primitives. Arbitrary application code does not automatically become durable simply because it runs on the runtime.

## Durable steps and replay

A workflow can divide work into durable steps. The runtime records completed step results. On recovery, completed durable steps can be replayed from their recorded results while unfinished work is executed again.

**Sales-safe explanation:** "The workflow can recover from recorded progress, rather than requiring the application to reconstruct every completed operation itself."

Avoid saying: "Restate automatically saves every line of code, every LLM call, and every tool call." The application must use the durable APIs and programming model correctly.

## Durable timers and waiting

Long-running workflows may need to wait for a future time or an external event, such as a human approval. Durable waiting primitives can support that pause-and-resume pattern without requiring a developer to keep a worker process occupied.

The application still owns its approval interface, authorization rules, business logic, and user experience.

## Virtual Objects

Restate Virtual Objects provide a way to model keyed, stateful entities and coordinate access to their state. They can be useful when operations associated with the same logical entity need controlled, consistent processing.

Do not describe Virtual Objects as a universal tenant rate limiter or equate them with every form of concurrency control. The exact behavior depends on the application model and configuration.

## Flow control

Flow-control capabilities can help manage throughput and concurrency for work. The application and engineering team still need to define suitable policies based on downstream capacity, service-level objectives, and rate limits.

Avoid claiming that Restate automatically discovers every external API's rate limit or configures the customer's ideal policy.

## Failure recovery and external side effects

Durable execution can improve recovery of workflow logic, but it cannot guarantee exactly-once effects in arbitrary external systems.

Example:
1. The application sends a journal-entry request to an external accounting API.
2. The external system commits the journal entry.
3. The response is lost before the workflow records success.
4. The workflow retries the operation.

Without a suitable idempotency key, deduplication mechanism, or reconciliation strategy, the retry may create a duplicate side effect.

**Correct framing:** durable execution helps manage workflow progress; the application must still make external side effects safe through idempotency, deduplication, or reconciliation where supported.

## Discovery prompts

- Which parts of your workflow need to survive process restarts?
- How do you persist progress across multi-step jobs today?
- Which steps are safe to retry, and which create external side effects?
- How do you handle an API write that succeeds but whose response is lost?
- What does your team currently maintain for timers, retries, and workflow state?
