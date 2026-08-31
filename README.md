# Hackathon Idea Library

A private research library for finding strong, defensible hackathon products before implementation begins.

The working catalog is in [ideas.md](ideas.md). It contains product blueprints, winning mechanics, failure risks, showcase moments, and source projects gathered from public hackathons and builder portfolios.

The reusable Codex workflow is in [`skills/hackathon-winner`](skills/hackathon-winner). It combines idea selection, sponsor-fit pressure testing, build sequencing, demo planning, submission checks, and retrospectives into an installable skill.

Install it with:

```bash
npx skills add 0xZorak/hackathon-idea-library --skill hackathon-winner
```

Invoke it with `$hackathon-winner`, or ask Codex to evaluate a hackathon idea, choose between concepts, or plan a judge-facing demo.

## The filter

An idea belongs here only when it has:

1. a one-line explanation;
2. a visible user pain;
3. a reason the chosen technology is indispensable;
4. a demo moment judges can verify;
5. an honest reason it could fail; and
6. links or named sources that make the inspiration traceable.

If the product can be built just as well without the featured technology, it should be rejected or redesigned.

## How to use it

- Start with the pain, not a protocol feature.
- Combine mechanics from different projects instead of cloning one submission.
- Reduce the first version to a single end-to-end proof.
- Make the winning claim independently verifiable.
- Record new research in `ideas.md`, then commit the change with the source in the message.

## Privacy

This repository is private because it is an internal product-research notebook. The referenced source projects remain public and should always be credited when their mechanics influence a build.
