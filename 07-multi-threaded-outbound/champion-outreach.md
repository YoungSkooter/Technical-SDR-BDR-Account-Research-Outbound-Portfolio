# Champion Outreach: Senior Engineer

## Objective

Start a relevant technical conversation with an engineer close to the workflow. The goal is discovery, not an immediate product pitch.

## LinkedIn connection request

Hi {{FirstName}} — I was looking at Ramp's public work around accounting automation and multi-step workflows. I'm researching how engineering teams preserve workflow progress across external API calls and approval pauses. Thought it would be useful to connect.

## Follow-up after connection

Thanks for connecting, {{FirstName}}.

One edge case I've been thinking about in accounting workflows: an external write succeeds, but the caller loses the response before recording completion. The retry then has an uncertain outcome unless the operation is idempotent or reconciled.

Curious how your team approaches durable progress and safe retries across those boundaries?

## Email option

**Subject:** Workflow recovery across accounting integrations

Hi {{FirstName}},

I was reading about Ramp's accounting automation direction and the workflows involved in moving from reconciliation through review and downstream accounting actions.

One tricky distributed-systems edge case is an external write that succeeds while the calling worker loses the response. The workflow may need to recover without repeating a side effect.

How does your team handle durable progress and idempotency across those external-system boundaries today?

I'm researching durable execution patterns and thought the question might be relevant to the work your team is doing.

Best,  
{{YourName}}

## Personalization requirements

Before sending:
- Verify the recipient's current role and team.
- Confirm that the public product context is still accurate.
- Remove any wording that implies knowledge of private incidents.
- Do not claim to have built or attached a code sample unless it exists and has been tested.
- Keep the message focused on one workflow question.
