---
name: terminate
description: Kill a timeline and archive to graveyard
---

# /terminate — Timeline Death

Manually terminate a timeline. Use when a timeline is clearly failing or exploring a dead-end approach.

## Usage

```
/terminate γ               # Terminate timeline γ
/terminate γ --reason="approach not viable"
```

## Process

```
TERMINATION
══════════════════════════════════════════════════════════════
Timeline-γ marked for termination.

Current state:
  Generation: 003
  Fitness: 34 (CRITICAL)
  Trend: 52 → 41 → 34 (declining)
  
Genome at death:
  traits: aggressive:0.8, experimental:0.6
  skills: react:0.7

AUTOPSY
──────────────────────────────────────────────────────────────
Cause of death: Manual termination (user)
Contributing factors:
  - aggressive:0.8 without defensive trait
  - Experimental approach generated unstable code
  - No testing skill to catch issues

Learnings extracted:
  ⚠ "aggressive > 0.7 requires defensive ≥ 0.4"
  ⚠ "experimental needs testing skill"

HIGH-RISK genes flagged:
  [aggressive:0.8, experimental:0.6] without [defensive, testing]

ARCHIVED: .claude/flux/graveyard/a3f7b2c1-γ.md

Timeline-γ has returned to the void.
══════════════════════════════════════════════════════════════
```

## When to Terminate

- Fitness declining for 3+ generations
- Approach proven unviable
- Resources better spent on other timelines
- Clear genetic failure pattern

## The Void Remembers

Terminated timelines are not deleted. Their patterns are archived and can be:
- Analyzed for failure patterns
- Partially resurrected (specific traits)
- Used to avoid future mistakes
