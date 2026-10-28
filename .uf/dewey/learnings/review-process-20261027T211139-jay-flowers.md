---
tag: review-process
author: jay-flowers
category: gotcha
created_at: 2026-10-27T21:11:39Z
identity: review-process-20261027T211139-jay-flowers
tier: draft
---

A spec-artifact defect captured only as a Dewey learning is not a remediation item. On opsx/replicator-version-floor (2026-10-27), the specs-mode review observed the proposal/delta capability three-way mismatch (declared New `replicator-version-floor` with no delta dir; declared Modified `doctor-replicator-group` with no main spec in openspec/specs/; actual delta `specs/doctor-replicator/` matching neither declaration) and stored it as learning openspec-20261027T154826 — but the round-1 code fix loop consumed only the code-round findings, so the mismatch reached the PR and the archive boundary unfixed. Fix loops consume findings and tasks, not the knowledge base. Rule: when a review round observes an artifact defect, surface it as a structured finding in that round's consolidated payload (or a tasks.md item) even when the insight is also stored as a learning; otherwise the knowledge is preserved while the defect ships.
