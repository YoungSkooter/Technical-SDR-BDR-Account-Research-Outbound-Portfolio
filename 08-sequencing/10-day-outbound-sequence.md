# Ten-Day Outbound Sequence

## Campaign objective

Create a qualified technical conversation about durable execution for multi-step workflows. The sequence uses two related personas:
- **Track A:** Senior Backend / AI Engineer (potential champion).
- **Track B:** Staff / Principal Engineer or Platform Lead (technical evaluator).

The cadence is a starting point, not a universal rule. Adapt to channel availability, local outreach regulations, recipient preferences, and actual engagement.

## Track A — Technical champion

| Day | Channel | Touch | Purpose |
|---|---|---|---|
| 1 | LinkedIn | Connection request referencing public accounting automation context | Establish relevance |
| 3 | LinkedIn | Ask about durable progress and safe retries across external writes | Start discovery |
| 6 | Email | Explain the uncertain external-write outcome in a concise example | Add technical insight |
| 8 | Phone, if appropriate | Briefly ask who owns workflow execution | Find ownership |
| 10 | Email | Close the loop with a respectful final question | End cadence cleanly |

### Day 1 — Connection
Use the connection request in `07-multi-threaded-outbound/champion-outreach.md`.

### Day 3 — Discovery
Ask how the team handles the case where an external write succeeds but the response is lost.

### Day 6 — Technical insight
Explain the distinction between durable workflow progress and idempotency at the external system boundary. Do not claim to have a demo or code sample unless one has actually been built and tested.

### Day 8 — Call
Only call a legitimate business number where appropriate. Keep it brief:
"I'm trying to understand who owns durable workflow execution for accounting automation. Is that within your team, or should I speak with someone in platform engineering?"

### Day 10 — Close
Hi {{FirstName}},

I'll close the loop here. I was reaching out because multi-step accounting workflows can raise interesting questions around durable progress and safe external writes.

If workflow execution is already well covered, no problem. If it's an area your team is reviewing, I'd be glad to compare notes.

Best,  
{{YourName}}

## Track B — Technical evaluator

| Day | Channel | Touch | Purpose |
|---|---|---|---|
| 1 | Email | Ask who owns workflow orchestration | Identify ownership |
| 4 | Email | Add a focused point about external side effects and recovery | Demonstrate technical understanding |
| 7 | Email or LinkedIn | Ask about current approach and evaluation criteria | Qualify architecture context |
| 9 | Phone, if appropriate | Confirm ownership or ask for referral | Advance discovery |
| 10 | LinkedIn | Brief close-the-loop message | End cadence respectfully |

### Day 1 — Ownership question
Use the decision-maker email in `07-multi-threaded-outbound/decision-maker-outreach.md`.

### Day 4 — New insight
"One subtle point in durable workflow design is that recovering workflow progress and guaranteeing an external side effect are separate concerns. If an API write commits but the response is lost, the application still needs idempotency or reconciliation. Is that boundary something your team standardizes centrally?"

### Day 7 — Evaluation criteria
"If your team ever evaluates a durable execution runtime, what tends to matter most: programming model, operational ownership, deployment, or how it fits the existing workflow architecture?"

### Day 9 — Call
Ask whether the person owns the relevant architecture. If not, request the appropriate role or team rather than pressing for a meeting.

### Day 10 — Close
"Thanks for considering this. I'll leave it here for now. If durable workflow execution becomes a priority, happy to reconnect."

## Engagement rules

- Stop the automated cadence when a recipient replies.
- If the recipient asks not to be contacted, stop outreach to that person.
- Do not send the same message to multiple people at the same company without adapting it.
- Do not disclose one employee's private comments to another without permission.
- Do not pause all account outreach automatically because one person replies; adjust based on what was learned and avoid duplicate or contradictory messages.
- Keep every touch useful. Do not send a follow-up that merely says "bumping this."
