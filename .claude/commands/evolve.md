---
name: evolve
description: Advance all timelines one generation - apply mutations based on fitness
---

# /evolve — Generation Advancement

Advance all active timelines to their next generation. Each timeline's current generation is evaluated, mutations are applied, and successors are spawned.

## Usage

```
/evolve                    # Evolve all active timelines
/evolve α                  # Evolve only timeline α
/evolve --auto             # Automatic evolution until convergence
```

## Process

### 1. Invoke FLUX-CORE

```
Use flux-core to evolve active timelines.

FLUX-CORE should:
1. Find all active timelines in current evolution
2. For each timeline:
   a. Calculate fitness of current generation
   b. Check termination conditions
   c. Generate mutations
   d. Spawn next generation
3. Report results
```

### 2. Fitness Calculation

For each active generation:

```
FITNESS CALCULATION
═══════════════════════════════════════
Timeline-α, gen-002

Task metrics:
  Task completed:      +100
  Tests pass:          +100
  Code runs:           +50
  
Efficiency:
  Tokens (2.3k):       -2
  Steps (8):           -40
  Errors (1):          -10
  
Quality:
  Code elegance (4/5): +80
  User feedback:       +0
  
TOTAL FITNESS: 278 → normalized: 78
═══════════════════════════════════════
```

### 3. Termination Check

```python
if fitness < 20:
    terminate(timeline)
    
if fitness_declining_for(2_generations):
    option_a: backtrack to previous gen
    option_b: terminate timeline
```

### 4. Mutation Generation

Based on fitness and self-analysis:

```
MUTATIONS PROPOSED
═══════════════════════════════════════
Timeline-α, gen-002 → gen-003

Self-proposed (from gen-002):
  "I noticed edge cases in error handling"
  → TRAIT_ADD: defensive (0.4)

Algorithmic (based on fitness):
  → TRAIT_ADJUST: analytical 0.6 → 0.7
  → PROMPT_MODIFY: Add "verify assumptions"
  
Fitness-based:
  → SKILL_ADD: testing (0.5) - errors detected
═══════════════════════════════════════
```

### 5. Next Generation Spawned

```
EVOLUTION COMPLETE
══════════════════════════════════════════════════════════════

Timeline-α: gen-002 → gen-003
  Fitness: 62 → 78 (+16) ▲
  Mutations: +defensive, +analytical, +testing
  Status: HEALTHY
  
Timeline-β: gen-002 → gen-003  
  Fitness: 71 → 74 (+3) ─
  Mutations: minor prompt adjustments
  Status: STABLE
  
Timeline-γ: gen-002 → TERMINATED
  Fitness: 45 → 18 (-27) ▼
  Cause: Fitness below threshold
  Archived: .claude/flux/graveyard/a3f7b2c1-γ.md
  Learnings extracted.

Active timelines: 2
Terminated this cycle: 1

Next: /evolve again, /cross α β, or /select
══════════════════════════════════════════════════════════════
```

## Auto-Evolution

```
/evolve --auto
```

Continues evolving until:
- One timeline reaches fitness > 90
- All timelines stagnate (no improvement for 3 gens)
- User interrupts

## Backtracking

If fitness decreases but timeline shows promise:

```
BACKTRACK OPTION
═══════════════════════════════════════
Timeline-β declining: 74 → 68 → 61

Options:
[A] Backtrack to gen-002 (fitness 74), try different mutations
[B] Continue with current trajectory
[C] Terminate timeline

Select: 
```

## Manual Mutation

Override algorithmic mutations:

```
/evolve α --add-trait=creative:0.5 --remove-skill=legacy
```

## Tips

- Watch for stagnation (small fitness changes)
- Declining timelines may need crossover, not just mutation
- High fitness (>85) may be local maximum - consider mutation spike
- Check graveyard for patterns - avoid repeating failures
