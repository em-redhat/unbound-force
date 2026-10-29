---
tag: test-quality
author: jay-flowers
category: pattern
created_at: 2026-10-27T21:11:49Z
identity: test-quality-20261027T211149-jay-flowers
tier: draft
---

A design doc that sanctions a deliberate divergence from a sibling implementation's semantics pins the decision in prose only unless a test row exercises the divergent input — and prose-only pinning is half a decision. In unbound-force's replicator-version-floor change, design D4 documents that parseVersionTriple accepts padded cores (v0.07.0 orders as 0.7.0) as a deliberate divergence from the sibling parseSemverComponent, which rejects leading-zero components; the divergence was documented in review round 1, but through rounds 2 and 3 no test table ever gained a padded-core row. A future consistency refactor toward the sibling's stricter semantics would pass the full suite while silently flipping documented behavior. Review check: for every "deliberate divergence" or "rejected reuse because semantics differ" note in a design's alternatives analysis, grep the test tables for the divergent input; if absent, flag a LOW unpinned-divergence gap. Complements learning test-quality-20261027T182852 (design matrices describe intent, not coverage completeness): that rule covers behaviors added during implementation; this one covers behaviors the design explicitly chose to keep different from an existing implementation.
