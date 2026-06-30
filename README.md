# Flux

[![Support me on Patreon](https://img.shields.io/badge/Patreon-Support%20my%20work-FF424D?style=flat&logo=patreon&logoColor=white)](https://www.patreon.com/AndersBjarby)

FLUX is an evolutionary system for Claude Code where intelligence fragments compete, mutate, crossbreed, and die. Instead of writing fixed agents, you grow them: solutions emerge through natural selection across parallel timelines. The same "gene" can be lethal in one context and beneficial in another, so FLUX tracks contextual risk rather than flat rejections.

## What it does

- **Parallel timelines** — fork several fundamentally different approaches and evolve them generation by generation
- **Context detection** — classifies the problem (security-critical, prototyping, creative, …) and filters genes accordingly
- **The graveyard** — failed experiments are kept with per-context risk profiles, acting as an immune system, not a trash bin
- **Safety genes** — risky traits (aggressive, experimental, creative) require defensive/testing/methodical partners or failure rates spike
- **Gaming detection** — flags agents that game fitness metrics (passing tests with near-zero coverage, empty catch blocks, stubbed "complete" tasks)
- **Crossover** — combine the best traits from successful timelines

## Commands

- `/explore "<problem>"` — fork timelines and begin evolution
- `/evolve` — advance all timelines one generation
- `/status` — view the fitness landscape
- `/cross α β` — crossbreed two timelines
- `/select` — end evolution and select the winner
- `/terminate <timeline>` — kill a timeline
- `/resurrect <id>` — revive from the graveyard (context-aware)

## Quick start

This is a Claude Code project — open it with Claude Code and use the slash commands.

```bash
claude
/explore "Build a REST API with authentication"
/status     # watch the fitness landscape
/evolve     # advance generations
/cross α β  # breed promising timelines
/select     # choose a winner
```

## Tech

Claude Code (CLAUDE.md, a `flux-core` agent, slash commands, and a `.claude/flux/genome` of trait and skill genes plus evolution/graveyard/winners directories). Markdown-based; no build step.
