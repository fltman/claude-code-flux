---
name: status
description: View evolution state - all timelines, fitness scores, and progress
---

# /status — Evolution Observatory

View the current state of all timelines, fitness trajectories, and evolution progress.

## Usage

```
/status                    # Full overview
/status α                  # Detail on timeline α
/status --fitness          # Fitness comparison only
/status --genome           # Genome comparison
```

## Output

```
FLUX STATUS
══════════════════════════════════════════════════════════════
Evolution: a3f7b2c1
Problem: "Build authentication system"
Started: 2025-01-15 10:30
Generations evolved: 12

ACTIVE TIMELINES
──────────────────────────────────────────────────────────────
       Timeline  Gen  Fitness  Trend    Genome Summary
──────────────────────────────────────────────────────────────
    α  JWT       004  ███████░  78 ▲    analytical:0.8 defensive:0.5
    β  Sessions  003  ██████░░  71 ─    methodical:0.7 testing:0.6
    δ  Hybrid    002  ████████  84 ▲▲   analytical:0.7 creative:0.5
──────────────────────────────────────────────────────────────

FITNESS TRAJECTORIES
──────────────────────────────────────────────────────────────
α: 45 → 58 → 67 → 78        [climbing]
β: 52 → 71 → 74 → 71        [plateau] 
δ: 76 → 84                  [strong start - crossover child]
──────────────────────────────────────────────────────────────

TERMINATED (Graveyard)
──────────────────────────────────────────────────────────────
γ: Passwordless  gen-002  fitness:18  [aggressive without safety]
──────────────────────────────────────────────────────────────

OBSERVATIONS
──────────────────────────────────────────────────────────────
• δ (crossover of α+β) outperforming parents
• β stagnating - consider mutation spike or crossover
• α approaching potential local maximum (78)
• γ's failure pattern: aggressive:0.9 without defensive

SUGGESTIONS
──────────────────────────────────────────────────────────────
• Continue evolving δ - strong trajectory
• Consider /cross α δ - combine approaches
• Timeline β may benefit from creative trait injection
══════════════════════════════════════════════════════════════
```

## Timeline Detail

```
/status α

TIMELINE-α DETAIL
══════════════════════════════════════════════════════════════
Approach: JWT-based stateless auth
Current generation: 004
Fitness: 78 (HEALTHY)

GENOME
  Traits:
    analytical:  ████████░░  0.8
    defensive:   █████░░░░░  0.5
    methodical:  ████░░░░░░  0.4
  Skills:
    api-design:  ████████░░  0.8
    testing:     ██████░░░░  0.6
    security:    █████░░░░░  0.5

EVOLUTION HISTORY
  gen-001: 45  [initial spawn]
  gen-002: 58  [+analytical, +api-design]
  gen-003: 67  [+defensive, +testing]
  gen-004: 78  [+methodical, refined prompts]

MUTATIONS THIS GENERATION
  • analytical: 0.7 → 0.8
  • Added methodical: 0.4
  • Prompt: "verify token signatures"

SELF-ASSESSMENT (from gen-004)
  "Performance good on happy path. 
   Edge cases in token refresh need work.
   Suggest: increase defensive or add caching skill"

COMPATIBLE FOR CROSSOVER WITH
  • β (sessions) - complementary approaches
  • δ (hybrid) - could reinforce strengths
══════════════════════════════════════════════════════════════
```

## Fitness Comparison

```
/status --fitness

FITNESS COMPARISON
══════════════════════════════════════════════════════════════
Timeline  Gen  Current  Peak   Trend   vs Peak
──────────────────────────────────────────────────────────────
δ Hybrid  002    84      84     ▲▲      at peak
α JWT     004    78      78     ▲       at peak  
β Session 003    71      74     ▼       -3 from peak
──────────────────────────────────────────────────────────────

LEADER: δ (Hybrid) - crossover of α + β
GAP: δ leads α by 6, β by 13

PROJECTION (based on trajectory):
  δ: likely to reach 90+ in 2-3 generations
  α: may plateau around 80-82
  β: needs intervention or will decline
══════════════════════════════════════════════════════════════
```

## Genome Comparison

```
/status --genome

GENOME COMPARISON
══════════════════════════════════════════════════════════════
Trait          α      β      δ     
──────────────────────────────────────────────────────────────
analytical    0.8    0.3    0.7    δ inherited from α
creative      0.0    0.2    0.5    δ got mutation
methodical    0.4    0.7    0.5    averaged
defensive     0.5    0.4    0.5    maintained
cautious      0.2    0.5    0.3    averaged

Skill          α      β      δ
──────────────────────────────────────────────────────────────
api-design    0.8    0.7    0.8    max inherited
testing       0.6    0.6    0.7    boosted in δ
postgres      0.0    0.6    0.3    partial inherit
security      0.5    0.3    0.4    averaged

UNIQUE COMBINATIONS
  α: High analytical + api-design (systematic API)
  β: High methodical + postgres (structured data)
  δ: Balanced + creative (innovative hybrid)
══════════════════════════════════════════════════════════════
```
