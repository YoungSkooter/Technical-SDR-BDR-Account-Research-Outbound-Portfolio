# Technical Pain Mapping: Accounting Workflow Failure Scenario

## Scenario status

**Hypothesis only.** This is a plausible failure scenario designed to create a useful discovery conversation. It is not a claim that Ramp has experienced this failure or uses the described internal architecture.

## Illustrative workflow

1. An accounting automation workflow begins.
2. It retrieves financial records and performs reconciliation.
3. It identifies an exception or prepares an accounting action.
4. It waits for a human reviewer or CPA.
5. After approval, it sends a journal-entry request to an external accounting system.
6. It records completion and advances the workflow.

## Failure window

Consider this sequence:
- The application sends a journal-entry write request.
- The external accounting system commits the write.
- The response is lost or the calling worker crashes before the workflow records success.
- The application retries because it cannot distinguish "the write failed" from "the write succeeded but the response was lost."

If the external operation is not protected, a retry may create a duplicate side effect.

## Why this is difficult

The application must distinguish:
- Work that has definitely completed.
- Work that has not started.
- Work whose outcome is uncertain.
- Work that can be retried safely.
- Work that requires reconciliation before retrying.

The uncertain-outcome case is especially important for external side effects.

## What durable execution may help with

A durable execution runtime can help:
- Persist workflow progress across interruptions.
- Resume from recorded completed steps.
- Model long-running waits and timers.
- Make retry and recovery behavior more explicit.
- Reduce the amount of custom workflow state machinery developers maintain.

## What the application must still own

- Idempotency keys where the external API supports them.
- Application-side deduplication when appropriate.
- Reconciliation for uncertain outcomes.
- Correct business validation and authorization.
- Error classification and retry policy.
- Audit trails and domain-specific correctness.
- Handling of external APIs that do not support idempotency.

## Business impact hypothesis

If this class of problem is not handled well, possible consequences include:
- Manual cleanup and reconciliation.
- Delayed accounting workflows.
- Support escalations.
- Reduced trust in automation.
- Engineering time spent on recovery paths.

## Discovery questions

1. "How do you handle an external write when the request may have succeeded but the response was lost?"
2. "Which steps in your workflow are safe to retry, and which need idempotency or reconciliation?"
3. "How do workflows resume after a worker restart or deployment?"
4. "How do you represent human approval pauses in long-running processes?"
5. "How much custom infrastructure does the team maintain for state, retries, and timers?"

## SDR talk track

"I noticed the public focus on accounting automation and multi-step workflows. In systems that reconcile data, pause for approval, and then write to an external accounting platform, one tricky edge case is an API write that succeeds while the caller loses the response. I'm curious how your team handles durable progress and idempotency across that boundary."
