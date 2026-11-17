# Qualification Criteria

Use these criteria to decide whether an account deserves deeper research or a discovery conversation.

## 1. Workload fit

Strong indicators:
- Workflows span multiple steps, services, or external APIs.
- Processes may run for a long time or pause for human input.
- Failures require resuming from partial progress.
- The workload has important state transitions.
- Some operations are expensive or unsafe to repeat.

Questions:
- "Can you walk me through a workflow that runs across multiple services?"
- "Can it pause for a user or external event?"
- "What happens if a worker restarts halfway through?"

## 2. Current implementation

Strong indicators:
- Several components share responsibility for workflow state.
- Teams maintain custom retries, timers, and recovery.
- Queue redelivery and duplicate processing require substantial application logic.
- Developers have built an internal orchestration layer.

Questions:
- "Where does workflow state live today?"
- "Which system owns retries and delayed execution?"
- "How do you distinguish a completed external operation from one that timed out?"

## 3. Business impact

Strong indicators:
- Workflow failures affect customer-facing or financially important operations.
- Manual intervention is frequent or costly.
- Engineering velocity is affected by orchestration maintenance.
- Reliability requirements are increasing with product adoption.

Questions:
- "What is the operational consequence when this workflow gets stuck?"
- "How often does the team have to intervene manually?"
- "Is this a current engineering priority?"

## 4. Timing and trigger

Potential triggers:
- Launch of an AI agent or automation product.
- Expansion of multi-step integrations.
- Hiring for platform or distributed-systems roles.
- Migration from prototype to production.
- New reliability or scale requirements.
- Public product announcements describing complex workflows.

A trigger is a reason to research and ask—not proof of active buying intent.

## Qualification summary

Prioritize accounts where **workload complexity + visible pain + relevant owner + timing** overlap. If only technology keywords are present, keep the account in a research stage rather than treating it as qualified.
