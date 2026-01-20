---
name: explore
description: Begin temporal forking - spawn parallel timelines to explore a problem
---

# /explore — Begin Evolution

Initiate temporal forking for a complex problem. Multiple timelines will explore different fundamental approaches in parallel.

## Usage

```
/explore [problem description]
```

Or just `/explore` to be prompted.

## Process

### 1. Context Detection

Before forking, FLUX classifies the problem context:

```
CONTEXT DETECTION
══════════════════════════════════════════════════════════════
Problem: "Build authentication for banking API"

Detected signals:
  ✓ "banking" → financial context
  ✓ "API" → backend context  
  ✓ "authentication" → security-critical context

Applied context: SECURITY-CRITICAL

Graveyard filters activated:
  ⚠ aggressive > 0.6 → HIGH RISK (historical: -34% fitness)
  ⚠ experimental > 0.7 → MODERATE RISK without testing
  ✓ defensive → ENCOURAGED (+22% fitness in this context)
══════════════════════════════════════════════════════════════
```

Different contexts unlock different genes from the graveyard. What killed agents in security-critical contexts might thrive in creative exploration.

### 2. Invoke FLUX-CORE

```
Use flux-core to begin temporal forking.

Problem: [user's problem]

FLUX-CORE should:
1. Analyze the problem space
2. Identify 3+ fundamentally different approaches
3. Generate unique problem hash
4. Create directory structure
5. Compose initial genomes for each approach
6. Spawn gen-001 for each timeline
```

### 2. Problem Analysis

FLUX-CORE will identify orthogonal approaches. Examples:

**Problem**: "Build authentication"
- Timeline-α: "JWT-based stateless auth"
- Timeline-β: "Session-based server auth"
- Timeline-γ: "Passwordless magic links"

**Problem**: "Improve performance"
- Timeline-α: "Caching layer"
- Timeline-β: "Query optimization"
- Timeline-γ: "Architecture change"

### 3. Directory Creation

```
.claude/flux/evolution/[hash]/
├── problem.md              # Problem definition
├── timeline-α/
│   └── gen-001.md          # First generation
├── timeline-β/
│   └── gen-001.md
└── timeline-γ/
    └── gen-001.md
```

### 4. Genome Composition

Each timeline gets a tailored genome:

```yaml
# Timeline-α: JWT approach
genome:
  traits: [analytical: 0.7, defensive: 0.6]
  skills: [api-design: 0.8, security: 0.7]

# Timeline-β: Sessions approach  
genome:
  traits: [methodical: 0.7, cautious: 0.5]
  skills: [api-design: 0.7, postgres: 0.6]

# Timeline-γ: Passwordless approach
genome:
  traits: [creative: 0.7, experimental: 0.5]
  skills: [api-design: 0.6, react: 0.5]
```

### 5. Evolution Begins

```
FORK INITIATED
══════════════════════════════════════════════════════════════
Problem: "Build authentication system"
Hash: a3f7b2c1
Location: .claude/flux/evolution/a3f7b2c1/

Timeline-α: "JWT-based stateless auth"
  └── gen-001 spawned
      Genome: analytical:0.7, defensive:0.6, api-design:0.8
      Approach: Stateless tokens, no server session
      
Timeline-β: "Session-based server auth"
  └── gen-001 spawned
      Genome: methodical:0.7, cautious:0.5, postgres:0.6
      Approach: Server-side sessions, database storage
      
Timeline-γ: "Passwordless magic links"
  └── gen-001 spawned
      Genome: creative:0.7, experimental:0.5, react:0.5
      Approach: Email-based, no passwords

All timelines exploring in parallel.
Use /status to monitor. Use /evolve to advance generations.
══════════════════════════════════════════════════════════════
```

## Options

```
/explore --timelines=5        # More than default 3
/explore --approach="X"       # Force include specific approach
/explore --fast               # Skip genome optimization
```

## What Happens Next

1. Each timeline works on the problem with its approach
2. Run `/evolve` to advance generations (mutation + selection)
3. Run `/status` to see fitness scores
4. Run `/cross α β` if promising timelines could combine
5. Run `/select` when ready to choose winner

## Tips

- More different approaches = better exploration
- Let timelines fail - that's information
- Don't rush to select - let evolution work
- Watch for crossover opportunities
