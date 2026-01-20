---
name: cross
description: Crossover breeding - combine genomes from two timelines to create hybrid
---

# /cross — Genetic Crossover

Combine the successful traits from two timelines to create a hybrid timeline. This is often how breakthrough solutions emerge.

## Usage

```
/cross α β                 # Crossover timelines α and β
/cross α β --name=hybrid   # Name the offspring
/cross --suggest           # Get crossover suggestions
```

## Process

### 1. Invoke FLUX-CORE

```
Use flux-core to perform crossover breeding.

Parents: Timeline-α, Timeline-β

FLUX-CORE should:
1. Analyze both genomes
2. Check compatibility
3. Identify strongest traits from each
4. Combine into hybrid genome
5. Spawn new timeline
```

### 2. Compatibility Check

```
COMPATIBILITY ANALYSIS
══════════════════════════════════════════════════════════════
Timeline-α genome:
  traits: [analytical:0.8, defensive:0.5, methodical:0.4]
  skills: [api-design:0.8, testing:0.6, security:0.5]

Timeline-β genome:
  traits: [methodical:0.7, cautious:0.5, creative:0.2]
  skills: [api-design:0.7, postgres:0.6, testing:0.5]

Conflict check:
  ✓ No directly conflicting traits
  ✓ Skills are complementary
  ✓ Approaches can merge (stateless + stateful = hybrid)

Compatibility: HIGH
Recommended: PROCEED
══════════════════════════════════════════════════════════════
```

### 3. Trait Selection

```
TRAIT INHERITANCE
══════════════════════════════════════════════════════════════
Strategy: Select highest performing traits from each parent

From α (fitness 78):
  ✓ analytical: 0.8 (key to α's success)
  ✓ defensive: 0.5 (error handling)
  
From β (fitness 71):
  ✓ methodical: 0.7 (structured approach)
  ✓ cautious: 0.5 (safe operations)
  
Mutation (crossover bonus):
  + creative: 0.4 (novel combination may need creativity)

HYBRID TRAITS:
  analytical: 0.8  (from α)
  methodical: 0.7  (from β)
  defensive: 0.5   (from α)
  cautious: 0.5    (from β)
  creative: 0.4    (crossover mutation)
══════════════════════════════════════════════════════════════
```

### 4. Skill Combination

```
SKILL INHERITANCE  
══════════════════════════════════════════════════════════════
Strategy: Union of skills, weight = max(parent_a, parent_b)

api-design: max(0.8, 0.7) = 0.8
testing:    max(0.6, 0.5) = 0.6
security:   0.5 (only α had this)
postgres:   0.6 (only β had this)

HYBRID SKILLS:
  api-design: 0.8
  testing: 0.6
  postgres: 0.6
  security: 0.5
══════════════════════════════════════════════════════════════
```

### 5. Spawn Hybrid

```
CROSSOVER COMPLETE
══════════════════════════════════════════════════════════════
Parents:
  α (JWT, fitness 78)
  β (Sessions, fitness 71)

Offspring: Timeline-δ (Hybrid)
  Approach: "Stateless JWT with session fallback"
  
  Genome:
    traits: analytical:0.8, methodical:0.7, defensive:0.5,
            cautious:0.5, creative:0.4
    skills: api-design:0.8, testing:0.6, postgres:0.6,
            security:0.5

  Starting fitness: 76 (inherited baseline)
  
Location: .claude/flux/evolution/a3f7b2c1/timeline-δ/gen-001.md

Prediction: High potential - combines strengths of both parents
══════════════════════════════════════════════════════════════
```

## Crossover Suggestions

```
/cross --suggest

CROSSOVER OPPORTUNITIES
══════════════════════════════════════════════════════════════
Based on current fitness and genome analysis:

RECOMMENDED
  α × β → δ
    α brings: analytical, api-design, security
    β brings: methodical, postgres, cautious
    Combined: Comprehensive, balanced approach
    Predicted fitness: 75-85
    
POSSIBLE
  α × γ-graveyard → ε
    α brings: stability, testing
    γ brings: creative approach (from before failure)
    Risk: γ failed due to aggressive - need to exclude
    Predicted fitness: 60-75

NOT RECOMMENDED
  β × β (self-cross)
    No genetic diversity
    Would just clone with noise
══════════════════════════════════════════════════════════════
```

## Incompatible Crossover

```
/cross α γ

COMPATIBILITY WARNING
══════════════════════════════════════════════════════════════
Conflict detected:

α has: defensive: 0.5, cautious: 0.3
γ has: aggressive: 0.8, impulsive: 0.4

These trait combinations conflict directly.
Offspring would have unstable genome.

Options:
[A] Proceed anyway (high mutation risk)
[B] Cross with trait exclusion (remove aggressive from γ)
[C] Cancel crossover

Select:
══════════════════════════════════════════════════════════════
```

## Tips

- Crossover often produces better results than continued mutation
- Best candidates: high fitness but different approaches
- The "creative" trait is often added in crossover (novel combinations)
- Check graveyard for useful traits from failed timelines
- Multiple crossovers possible: (α × β) × γ = three-way hybrid
