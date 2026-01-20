---
name: select
description: End evolution and select the winning genome
---

# /select — Natural Selection

End the evolution process and select the winning timeline. The winner's genome is archived, learnings are extracted, and the evolution is complete.

## Usage

```
/select                    # Auto-select highest fitness
/select α                  # Force select timeline α
/select --compare          # Side-by-side before selecting
```

## Process

### 1. Invoke FLUX-CORE

```
Use flux-core to perform final selection.

FLUX-CORE should:
1. Gather all active timelines
2. Calculate final fitness scores
3. Select winner (or present for user choice)
4. Archive winner to winners/
5. Archive losers to graveyard/
6. Extract meta-learnings
7. Summarize evolution
```

### 2. Final Comparison

```
FINAL SELECTION
══════════════════════════════════════════════════════════════
Evolution: a3f7b2c1
Problem: "Build authentication system"

CANDIDATES
──────────────────────────────────────────────────────────────
Rank  Timeline  Gen   Fitness  Approach
──────────────────────────────────────────────────────────────
 1    δ Hybrid  003   ████████████░  94   JWT + session fallback
 2    α JWT     005   █████████░░░░  82   Pure stateless
 3    β Session 004   ████████░░░░░  76   Pure server-side
──────────────────────────────────────────────────────────────

RECOMMENDATION: Timeline-δ (Hybrid)
  Highest fitness: 94
  Origin: Crossover of α + β
  Generations: 3
  
  Key strengths:
  - Combined JWT speed with session reliability
  - Comprehensive error handling
  - Strong test coverage
  
Confirm selection? [Y/n/compare]
══════════════════════════════════════════════════════════════
```

### 3. Winner Archival

```
ARCHIVING WINNER
══════════════════════════════════════════════════════════════
Timeline-δ selected as winner.

Saving to: .claude/flux/winners/a3f7b2c1-winner.md

Winner genome:
  traits:
    analytical: 0.85
    methodical: 0.7
    defensive: 0.6
    creative: 0.5
    cautious: 0.4
  skills:
    api-design: 0.9
    testing: 0.8
    security: 0.7
    postgres: 0.5

Evolution path:
  α-gen001 → α-gen005 (fitness: 45→82)
      ↓
    cross
      ↓ 
  β-gen001 → β-gen004 (fitness: 52→76)
      ↓
    cross
      ↓
  δ-gen001 → δ-gen003 (fitness: 76→94) ★ WINNER

Winner archived. ✓
══════════════════════════════════════════════════════════════
```

### 4. Graveyard Archival

```
ARCHIVING NON-WINNERS
══════════════════════════════════════════════════════════════
Timeline-α (runner-up):
  Final fitness: 82
  Reason: Outperformed by hybrid offspring
  Valuable traits preserved: analytical:0.8
  Archived: .claude/flux/graveyard/a3f7b2c1-α.md

Timeline-β (third):
  Final fitness: 76
  Reason: Outperformed by offspring
  Valuable traits preserved: methodical:0.7, postgres
  Archived: .claude/flux/graveyard/a3f7b2c1-β.md

Timeline-γ (terminated earlier):
  Final fitness: 18
  Already in graveyard
  Learnings: aggressive without defensive = failure
══════════════════════════════════════════════════════════════
```

### 5. Meta-Learnings

```
EVOLUTION LEARNINGS
══════════════════════════════════════════════════════════════
Evolution: a3f7b2c1
Duration: 4 hours
Total generations: 15
Crossovers: 2
Terminations: 1

KEY INSIGHTS
──────────────────────────────────────────────────────────────
1. "Crossover outperformed pure lineages"
   - δ (hybrid) beat both parents
   - Suggests: try crossover earlier in evolution

2. "analytical + methodical + defensive = robust"
   - This trait combo appeared in top 2 performers
   - Mark as HIGH-VALUE combination

3. "aggressive without defensive = fragile"
   - γ failed with this combo
   - Mark as HIGH-RISK combination

4. "creative trait valuable post-crossover"
   - Added during crossover, contributed to innovation
   - Consider injecting creative in hybrid spawns

5. "postgres skill less critical than expected"
   - Winner has postgres:0.5 (low)
   - Problem didn't need heavy database work

TRAIT PERFORMANCE SUMMARY
──────────────────────────────────────────────────────────────
                     Winner (δ)  Runner-up (α)  Failed (γ)
analytical              0.85         0.8           0.3
methodical              0.7          0.4           0.2
defensive               0.6          0.5           0.0 ← !!!
aggressive              0.0          0.0           0.9 ← !!!
creative                0.5          0.0           0.4

Clear pattern: defensive:0 + aggressive:high = failure

SAVED: .claude/flux/evolution/a3f7b2c1/learnings.md
══════════════════════════════════════════════════════════════
```

### 6. Evolution Complete

```
EVOLUTION COMPLETE
══════════════════════════════════════════════════════════════
Problem: "Build authentication system"
Solution: Timeline-δ (Hybrid JWT + Session)
Fitness: 94

The winner genome is now available at:
.claude/flux/winners/a3f7b2c1-winner.md

To use this genome for future problems:
  /explore "new problem" --seed=a3f7b2c1

To resurrect specific traits from this evolution:
  /resurrect a3f7b2c1-α    # Get α's analytical approach
  /resurrect a3f7b2c1-β    # Get β's postgres expertise

Evolution statistics:
  Generations explored: 15
  Timelines explored: 4
  Crossovers performed: 2
  Terminations: 1
  Time elapsed: 4h 23m
  
The fittest survived. Evolution complete.
══════════════════════════════════════════════════════════════
```

## Force Selection

If you want to select a non-winner:

```
/select α

WARNING: Timeline-α (fitness 82) is not highest fitness.
Timeline-δ has fitness 94.

Reasons to override:
- α's approach better fits production constraints
- δ is too experimental for this use case
- User preference

Confirm force selection of α? [y/N]
```

## No Clear Winner

```
/select

NO CLEAR WINNER
══════════════════════════════════════════════════════════════
Top timelines have similar fitness:

  α: 78
  β: 76
  δ: 79

Difference < 5 points. Consider:
[A] Continue evolution (/evolve --auto)
[B] Crossover top performers (/cross α δ)
[C] Select manually
[D] Select δ (technically highest)

Select:
══════════════════════════════════════════════════════════════
```
