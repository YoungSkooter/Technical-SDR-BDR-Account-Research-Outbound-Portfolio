# Account Dossier: Ramp

## Account overview

**Company:** Ramp  
**Category:** Financial operations / spend management / accounting automation  
**Account exercise:** Evaluate whether Restate's durable-execution model could be relevant to workflows associated with Ramp's accounting automation products.

This is an independent prospecting exercise. It does not imply that Ramp is a Restate customer or that Ramp has confirmed a need for Restate.

## Public context selected for research

The research exercise focused on public Ramp material describing:
- Ramp Stack and its accounting automation direction.
- Workflow patterns such as reconciliation, accounting operations, and integrations with accounting systems.
- Engineering material discussing agentic or multi-step product workflows.

The exact product scope, launch details, integrations, and public claims should be rechecked against the linked primary sources before using this dossier in live outreach.

## Why the account may fit

Financial and accounting automation can involve:
- Multiple data sources and external systems.
- Multi-step business processes.
- Approval and review steps.
- Writes to systems of record.
- High expectations around correctness and auditability.

These characteristics can create a relevant environment for durable execution. They do not establish that Ramp's current implementation has a reliability gap.

## Workflow hypothesis to investigate

A possible accounting workflow might:
1. Retrieve and normalize financial data.
2. Reconcile transactions.
3. Identify exceptions.
4. Wait for a human reviewer or CPA to approve.
5. Create or update an accounting entry in an external system.
6. Record the result and continue the close process.

This is a conceptual workflow map, not a claim that Ramp implements it exactly this way.

## Potential technical question

"When a workflow spans reconciliation, a human approval pause, and a write to an external accounting system, how do you preserve progress and make the final side effect safe if a worker or API request fails?"

## Potential business relevance

If workflow recovery or side-effect handling is difficult, the consequences could include:
- Manual reconciliation and exception handling.
- Delayed close processes.
- Engineering effort spent maintaining custom orchestration.
- Reduced confidence in automation.
- Risk of duplicate or missing external writes if idempotency is not handled.

These are possible consequences to explore, not known Ramp incidents.

## Likely stakeholders

- Senior backend or product engineers working on accounting automation.
- Staff / Principal Engineers responsible for architecture.
- Engineering Managers or Directors responsible for production systems.
- Platform or AI infrastructure leaders, if those teams own workflow execution.
- VP Engineering or CTO-level leadership for strategic evaluation.

Validate actual ownership through role research and conversation.

## Account strategy

Lead with the public workflow context and a question about how the team handles durable progress and external side effects. Do not open by asserting that Ramp has duplicate journal entries, timeouts, Redis bottlenecks, or a particular orchestration stack.
