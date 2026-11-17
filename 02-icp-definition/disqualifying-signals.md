# Disqualifying and Low-Priority Signals

These signals do not always mean an account can never use Restate. They indicate that outreach should be deprioritized or that qualification needs more evidence.

## Likely poor fit

- The application consists mainly of short, stateless request-response operations.
- Workflows are simple and already handled reliably by existing platform features.
- There are few asynchronous or multi-step processes.
- The team has no meaningful need for durable state, retries, timers, or coordination.
- The product is not responsible for building or operating backend workflows.

## Existing solution may be sufficient

- The team has a mature workflow platform that meets its requirements.
- The team has no dissatisfaction or workload gap with its current orchestration system.
- A migration would add more operational complexity than it removes.
- The workload is already well served by a managed cloud service.

An existing competitor is not an automatic disqualifier. Explore workload-specific gaps before deciding.

## Organizational barriers

- No identifiable engineering owner.
- No relevant project or workload.
- No capacity to evaluate new infrastructure.
- Strong platform standardization that prevents introducing another runtime.
- Compliance, security, or deployment requirements that the product cannot meet.

## Research cautions

Do not infer that an account has poor reliability because it is hiring SREs. Do not infer that a company needs orchestration because it uses Kubernetes. Treat these as context signals and validate the actual workflow.
