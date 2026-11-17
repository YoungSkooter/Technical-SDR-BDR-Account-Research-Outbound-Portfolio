# Use Cases and Value Propositions

## 1. AI agent workflows

**Workflow pattern:** An agent performs several tool calls, uses model outputs, waits for external data, and may pause for human approval.

**Potential problem:** A failure midway through a long-running process can require custom state recovery. Repeating expensive or non-idempotent operations may create cost or correctness issues.

**Restate value hypothesis:** Durable workflow primitives can help preserve progress and coordinate retries, waits, and recovery.

**Discovery question:** "When an agent process is interrupted halfway through a multi-step task, how does your application know which work is safe to resume?"

## 2. Financial and accounting automation

**Workflow pattern:** Reconcile transactions, request approval, create accounting entries, and synchronize results with external systems.

**Potential problem:** The workflow may span multiple services and external APIs, with business-critical side effects.

**Restate value hypothesis:** Durable execution may reduce custom orchestration work around long-running steps and human approval.

**Discovery question:** "How do you manage workflow state when a financial operation needs approval or an external API call times out?"

## 3. Backend business processes

**Workflow pattern:** Provisioning, onboarding, order processing, document processing, or multi-service coordination.

**Potential problem:** Queues and ad hoc retry logic can become difficult to reason about as workflows grow more complex.

**Restate value hypothesis:** A durable execution model may simplify how developers implement long-running, recoverable business processes.

**Discovery question:** "How much of your application code is dedicated to retry, state persistence, and recovery rather than the business process itself?"

## 4. Distributed coordination

**Workflow pattern:** Multiple operations must coordinate around a shared entity, customer, account, or resource.

**Potential problem:** Concurrent requests and state transitions can create race conditions or require custom coordination.

**Restate value hypothesis:** Stateful coordination primitives may help developers model these interactions more clearly.

**Discovery question:** "Where do you need per-entity coordination, and how is that implemented today?"

## Value translation

| Technical capability | Possible engineering value | Possible business value |
|---|---|---|
| Durable progress | Less custom recovery logic | Engineering capacity for product work |
| Durable waiting/timers | Easier long-running workflows | More reliable customer processes |
| Controlled retries | More explicit failure handling | Fewer avoidable manual interventions |
| Stateful coordination | Clearer handling of keyed workflows | More predictable process behavior |
| Flow control | Better-managed throughput | Reduced risk of overwhelming dependencies |

All business outcomes should be quantified through discovery rather than asserted in cold outreach.
