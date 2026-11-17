# Objection Handling

## "We already use Temporal."

**Response:**

"That makes sense—Temporal is a serious durable workflow platform. I'm not assuming you need to replace it. Are there particular workloads where the programming model, deployment approach, or operational ownership creates friction, or is it working well for the use cases you have?"

**Why it works:** Acknowledges the incumbent and looks for a specific gap rather than making an inaccurate comparison.

## "We use queues and retries already."

**Response:**

"That may be all you need. I'm curious where workflow state lives beyond the queue message—especially if a process pauses for approval or spans several services. Is that handled in an existing workflow layer, or is it custom application logic?"

**Why it works:** Distinguishes message delivery from the broader workflow lifecycle.

## "We can build this ourselves."

**Response:**

"Absolutely. The question is whether building and maintaining the state, timers, recovery, and coordination layer is worth it for your team. How much of that machinery is already in place, and is it becoming a maintenance burden?"

**Why it works:** Respects engineering capability and explores opportunity cost.

## "We don't have this problem."

**Response:**

"Understood. If your current workflows are short-lived and your existing retry model is working, there may not be a reason to add another runtime. Are there any long-running or human-in-the-loop processes where the requirements are different?"

**Why it works:** Accepts a genuine no-fit signal and checks one relevant boundary.

## "How does Restate prevent duplicate external writes?"

**Response:**

"Durable execution helps the workflow recover from recorded progress, but it doesn't automatically guarantee exactly-once effects in every external system. If an external API commits a write and the response is lost, the application still needs an idempotency key, deduplication, or reconciliation strategy. That's an important design boundary."

**Why it works:** Technically accurate and trust-building.

## "We use AWS Step Functions."

**Response:**

"That may be a good fit, especially if it matches your AWS architecture and workflow requirements. What matters most in your evaluation—developer experience, deployment model, integration with application code, operational ownership, or cost at your workload scale?"

**Why it works:** Avoids dismissing a legitimate alternative.

## "Send me information."

**Response:**

"Happy to. To make it relevant, is your main interest long-running workflow recovery, human approval and timers, or coordinating stateful operations across services?"

**Why it works:** Qualifies the information request before sending generic material.
