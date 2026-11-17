# Persona Messaging

## Senior Backend / AI Engineer

**What they care about:** Shipping features, understandable code, fewer custom recovery paths, and predictable behavior when a workflow is interrupted.

**Message angle:** "How much code does your team maintain around workflow state, retries, and resuming long-running jobs?"

**Discovery questions:**
- "Which workflow is hardest to resume after a process restart?"
- "How do you know which steps are safe to repeat?"
- "Are you using a workflow runtime, or building this into the application?"

**Avoid:** Suggesting that the engineer's current system is broken or that Restate automatically persists arbitrary code.

## Staff / Principal Engineer

**What they care about:** Correctness, architecture, operational trade-offs, concurrency, failure semantics, and long-term maintainability.

**Message angle:** "For workflows that combine durable state, external side effects, and human approval, how are you separating workflow recovery from idempotency at the system boundary?"

**Discovery questions:**
- "Which component owns workflow state and retry policy?"
- "How do you handle uncertain outcomes from external writes?"
- "What would make you consider a dedicated durable execution runtime?"

**Avoid:** Unfair Temporal comparisons, unsupported scale assumptions, or claiming a specific internal architecture.

## Engineering Manager / Director

**What they care about:** Team focus, production reliability, maintainability, incident burden, and delivery priorities.

**Message angle:** "Is maintaining orchestration and recovery logic taking meaningful engineering capacity away from product work?"

**Discovery questions:**
- "How much engineering effort goes into keeping long-running workflows reliable?"
- "Where do manual recovery tasks show up?"
- "Is workflow reliability an active priority this quarter?"

**Avoid:** Invented productivity savings or unverified incident claims.

## VP Engineering / CTO

**What they care about:** Product velocity, customer trust, cost, strategic infrastructure decisions, and execution risk.

**Message angle:** "As automation becomes more central to the product, is the team investing in a reusable execution layer or maintaining workflow reliability inside each service?"

**Discovery questions:**
- "Is workflow reliability becoming a platform-level concern?"
- "What would justify standardizing a durable execution approach?"
- "Which product initiatives are constrained by workflow complexity?"

**Avoid:** Leading with low-level implementation details or implying a confirmed business problem.

## Message structure

1. Publicly observable product or engineering context.
2. A concise technical observation.
3. A possible implication, clearly framed as a question.
4. One low-friction discovery question.
