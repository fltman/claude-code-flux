---
name: resurrect
description: Revive a terminated timeline or extract traits from graveyard
---

# /resurrect — Rise from the Void

Bring back a terminated timeline, or extract useful traits from failed experiments. The void remembers—and now it remembers **context**.

## The Ghost in the Graveyard

A gene that was toxic in one context might be a survival gene in another:

```
aggressive: 0.9
  └── LETHAL in banking API (killed Timeline-γ, evolution #23)
  └── BENEFICIAL in hackathon prototype (+41% fitness boost)
```

Before flat-rejecting a gene, FLUX now asks: **does this context match the death context?**

## Usage

```
/resurrect γ                       # Full resurrection
/resurrect γ --traits-only         # Extract traits, new timeline
/resurrect γ --into=α              # Merge γ's traits into α
/resurrect --list                  # List graveyard contents
```

## List Graveyard

```
/resurrect --list

THE VOID CONTAINS
══════════════════════════════════════════════════════════════
Evolution: a3f7b2c1

ID          Timeline  Final   Cause           Useful Traits
──────────────────────────────────────────────────────────────
a3f7b2c1-γ  Passwd    18     low fitness     creative:0.7
a3f7b2c1-ε  Cache     45     not selected    performance:0.8
──────────────────────────────────────────────────────────────

Previous evolutions:
7b2c1a3f-α  REST      72     superseded      api-design:0.9
7b2c1a3f-β  GraphQL   68     not selected    schema:0.8
══════════════════════════════════════════════════════════════
```

## Full Resurrection

```
/resurrect γ

RESURRECTION
══════════════════════════════════════════════════════════════
Reviving: Timeline-γ (Passwordless)
Final state: gen-003, fitness 18

WARNING: This timeline failed due to:
  - aggressive:0.8 without defensive
  - experimental without testing
  
Resurrection options:
[A] Exact revival (same genome, restart evolution)
[B] Revised revival (fix known issues first)
[C] Cancel

Select: B

REVISED GENOME
──────────────────────────────────────────────────────────────
Original:
  aggressive: 0.8  →  removed (caused failure)
  experimental: 0.6  →  reduced to 0.4
  creative: 0.7  →  kept (valuable)
  
Added (learned from failure):
  + defensive: 0.5
  + testing: 0.5

New timeline: γ-v2
Starting fitness: 40 (estimated, based on revision)

RESURRECTED: .claude/flux/evolution/a3f7b2c1/timeline-γ-v2/gen-001.md
══════════════════════════════════════════════════════════════
```

## Trait Extraction

```
/resurrect γ --traits-only

TRAIT EXTRACTION
══════════════════════════════════════════════════════════════
Source: Timeline-γ (terminated)

Extractable traits:
  ✓ creative: 0.7 (high value, no conflicts)
  ✗ aggressive: 0.8 (flagged dangerous)
  ~ experimental: 0.6 (usable with caution)

Extract creative:0.7 into new timeline? [Y/n]

NEW TIMELINE: ζ (zeta)
  Approach: "Creative exploration with safety"
  Genome:
    creative: 0.7 (from γ)
    defensive: 0.5 (safety addition)
    analytical: 0.5 (balance)
  
SPAWNED: .claude/flux/evolution/a3f7b2c1/timeline-ζ/gen-001.md
══════════════════════════════════════════════════════════════
```

## Trait Injection

```
/resurrect γ --into=α

TRAIT INJECTION
══════════════════════════════════════════════════════════════
Source: Timeline-γ (creative: 0.7)
Target: Timeline-α (gen-005)

Compatibility check:
  α genome: analytical:0.8, defensive:0.5, methodical:0.4
  γ trait: creative:0.7
  
  ✓ No conflicts
  ✓ May improve α's innovation capacity
  
Apply creative:0.7 to α's next generation? [Y/n]

Timeline-α gen-006 will include:
  - All current traits
  + creative: 0.5 (injected at reduced weight)

This counts as a mutation, not crossover.
══════════════════════════════════════════════════════════════
```

## Cross-Evolution Resurrection

```
/resurrect 7b2c1a3f-α

CROSS-EVOLUTION RESURRECTION
══════════════════════════════════════════════════════════════
Source: Evolution 7b2c1a3f (different problem)
Timeline: α (REST API, fitness 72)

This timeline is from a DIFFERENT evolution.
Problem was: "Build REST API"
Current problem: "Build authentication"

Relevant traits:
  ✓ api-design: 0.9 (highly relevant)
  ~ rest-patterns: 0.8 (partially relevant)
  ✗ pagination: 0.6 (not relevant)

Import api-design:0.9 into current evolution? [Y/n]

Creating new timeline with imported knowledge...
══════════════════════════════════════════════════════════════
```

## Tips

- The void is a knowledge base, not just a graveyard
- Failed timelines often have valuable partial solutions
- Cross-evolution resurrection enables knowledge transfer
- Always review WHY something failed before resurrecting
- Revised revival > exact revival (learn from mistakes)
