# Execution and submission playbook

Use this reference for preparation, team structure, build sequencing, demo production, submission, and retrospectives.

## Prepare before the event

The team should already be able to:

- create branches, commit, push, merge, and resolve conflicts;
- deploy the intended stack end to end;
- use `.env` files, `.gitignore`, redacted examples, and secret scanning;
- read an error before asking an AI assistant to interpret it;
- recognize when generated code is unsafe or inconsistent with the codebase.

Do not learn routine Git, deployment, or secret management for the first time during the final hour.

## Choose a team shape

Give each critical path a clear owner even when everyone is a generalist. Useful ownership boundaries include product/demo, frontend, backend/protocol integration, and AI/data. Reliability matters more than raw brilliance under deadline pressure.

Solo building is viable for an experienced generalist using AI effectively. It is a poor default for a beginner who would have to learn the stack, manage scope, integrate, deploy, and present simultaneously.

When uncertainty is high and capacity allows it, prototype two competing ideas briefly, then converge on the stronger proof. Time-box this exploration and define the decision criterion beforehand; do not maintain two full products.

## Build the demo path first

Define one golden path:

1. the initial user action;
2. the organizer technology doing the irreplaceable work;
3. the visible result;
4. the independent proof;
5. one meaningful failure or guardrail.

Implement this path before peripheral dashboards, profiles, settings, marketplaces, social features, or extra sponsor tracks.

Maintain an honesty ledger:

- **Live:** executed against the real service or network.
- **Seeded:** real code using prepared input.
- **Mocked:** simulated dependency or response.
- **Simplified:** reduced production behavior.
- **Future:** not implemented.

Never present one category as another.

## Stop feature work before the deadline

Begin demo production when the core product is roughly 90% complete. The demo is not cleanup after the project; it is the judge-facing form of the project.

Before recording:

- freeze the golden path;
- prepare deterministic accounts, balances, inputs, and state;
- remove secrets and personal notifications;
- rehearse timing;
- verify links in a logged-out browser;
- capture explorer, transaction, proof, benchmark, or output evidence;
- prepare a local or recorded fallback for unstable dependencies;
- reserve time for upload, processing, forms, and submission review.

## Design the first minute

A reliable structure is:

1. **0–10 seconds:** one-line problem and product.
2. **10–20 seconds:** why the organizer technology makes it possible.
3. **20–50 seconds:** uninterrupted golden-path demo.
4. **50–60 seconds:** independently verifiable result and measurable outcome.

After the hook, use remaining time for architecture, integration depth, safety, limitations, and expansion. Do not begin with team introductions, a long market lecture, or a stack list.

Choose live demo, recorded video, slides, or a hybrid based on what most reliably shows this product. The fanciest format is not automatically the best.

## Submission quality gate

Verify:

- title and one-line pitch match everywhere;
- live URL works without the builder's session;
- repository access and license satisfy the rules;
- README contains setup, architecture, integration mapping, evidence, limitations, and team roles;
- demo video is within the required duration and publicly viewable;
- contract addresses, network labels, transaction links, and timestamps are correct;
- no key, token, private endpoint, seed phrase, or personal data is committed;
- sponsor and track selections are accurate rather than opportunistic;
- every required field is complete before the portal closes.

## Handle blockers

Under time pressure, reduce scope before changing the thesis. Preserve the organizer technology's central role. A simpler interaction that clearly demonstrates the sponsor stack is preferable to an ambitious world that never reaches the proof moment.

Pivot only when the golden path cannot be completed or demonstrated. Record the trigger, new scope, and features being abandoned so the pivot does not become additive chaos.

## After the result

Winning is probabilistic. Run a retrospective covering idea quality, sponsor depth, demo clarity, technical failures, submission mistakes, judge feedback, and unexplained outcomes.

Whether the project wins or loses:

- publish what was built when appropriate;
- thank and follow up with the few mentors, judges, or builders who were genuinely helpful;
- save reusable components and new idea seeds;
- decide whether the product deserves several more weeks;
- record the failure reason rather than rewriting history around the result.

Prizes are only one outcome. Skills, collaborators, ecosystem access, accelerators, user feedback, and a product worth continuing may be more valuable.

