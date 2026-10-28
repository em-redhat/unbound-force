---
tag: documentation-gate
author: jay-flowers
category: gotcha
created_at: 2026-10-27T21:11:43Z
identity: documentation-gate-20261027T211143-jay-flowers
tier: draft
---

When a review-finding fix files a missing tracking issue, updating the in-repo records (tasks.md gate task, CHANGELOG traceability line) and cross-referencing the new issue from its own body does NOT resolve the original gate issue's disposition line. Observed on opsx/replicator-version-floor PR-mode review (2026-10-27): round 2 filed unbound-force/website#337 and recorded both numbers in tasks.md 3.2, the CHANGELOG, and #337's body — but repo-local gate issue #844 kept its pre-filing Website conditional ("no website tracking issue known for this change") with zero comments and unticked acceptance boxes, so live gh-verification at the PR-mode council found the stale statement hours after the gate was substantively closed. Rule: the remediation for a missing-issue finding must edit every artifact that recorded the absence — the gate issue's disposition line (resolve the conditional to the filed number) and its acceptance checkboxes — not only the artifacts that record the presence. A stale "no issue known" line in an open tracking issue invites duplicate filings against the search-first convention. Verification corollary for Curator PR-mode runs: verify both gate issues live (gh issue view on the current repo AND unbound-force/website), checking not just existence but that the repo-local issue's Website disposition resolves to the website issue number. Extends documentation-gate-20261027T182839 (resolve-before-council rule) with the incomplete-remediation form.
