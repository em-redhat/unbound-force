---
tag: review-process
author: jay-flowers
category: gotcha
created_at: 2026-10-27T21:11:46Z
identity: review-process-20261027T211146-jay-flowers
tier: draft
---

Fix-loop blind spot for artifact-metadata findings: in the replicator-version-floor change (2026-10-27), specs-mode review correctly identified the three-way capability-name mismatch — proposal.md declaring New `replicator-version-floor` and Modified `doctor-replicator-group` versus a shipped ADDED delta at specs/doctor-replicator/spec.md against a capability absent from openspec/specs/ — but the round-2 delegated fix run (one judgment run applying all findings at once) repaired the website gate, docs surfaces, the Detail-field spec-visibility gap, and test extensions without reconciling the proposal/delta names, and code round 2 returned APPROVE WITH ADVISORIES without re-flagging it, so the mismatch shipped in the PR (flagged again at PR review). Rename/metadata findings in spec artifacts are invisible to code-focused fix runs and to `openspec validate` (ADDED deltas against new capability directories validate cleanly). Rule: when a specs-mode finding is routed to a fix loop, the next review round must re-verify artifact-name alignment explicitly — enumerate the proposal's New/Modified/Removed capability names and diff them against both the change's specs/ delta directories and the openspec/specs/ main-specs listing — before returning an approving verdict.
