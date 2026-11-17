# Product Overview: Restate

## Product category

Restate is best understood as **durable execution and workflow infrastructure**. It helps developers build applications whose workflows can continue reliably across failures, delays, retries, and asynchronous interactions.

It is not primarily an observability platform, a queue, or a general-purpose AI agent builder. It provides runtime primitives that application developers can use to implement reliable long-running processes.

## The problem

A modern backend workflow may:
- Call multiple internal services and external APIs.
- Invoke an LLM or other expensive computation.
- Wait for a person to approve an action.
- Pause for minutes, hours, or days.
- Retry after transient failures.
- Resume after a worker or process restarts.

Without a durable execution approach, teams may need to combine queues, databases, retry logic, state machines, locks, timers, and custom recovery code. This can increase implementation complexity and create more behavior for the team to test and operate.

## Core value proposition

Restate provides a runtime and programming model for durable workflows. Developers can structure work into durable steps and use primitives for stateful coordination, retries, and waiting. The runtime records progress so completed durable work does not need to be blindly repeated when execution resumes.

## Who may care

- Backend and distributed-systems engineers building long-running workflows.
- AI engineers orchestrating multi-step agent processes.
- Platform teams standardizing workflow reliability.
- Engineering leaders responsible for delivery speed and production reliability.

## Business outcomes to explore

- Less custom workflow and recovery infrastructure to maintain.
- More predictable recovery from transient failures.
- Easier implementation of long-running and human-in-the-loop processes.
- Reduced engineering effort spent rebuilding workflow state and retry behavior.
- Better control over how work is coordinated under load.

These are value hypotheses to validate with each prospect, not guaranteed outcomes or quantified claims.
