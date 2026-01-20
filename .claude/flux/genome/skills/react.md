---
skill: react
type: domain
default-weight: 0.7

provides-tools: [Read, Write, Edit, Bash]
synergizes-with: [creative, methodical, testing]

contextual-value:
  creative:
    value: BENEFICIAL
    historical-fitness: +28%
    recommendation: ENCOURAGE for UI work
  
  prototyping:
    value: BENEFICIAL
    historical-fitness: +22%
    recommendation: Fast component iteration
  
  performance:
    value: BENEFICIAL
    historical-fitness: +15%
    recommendation: For render optimization
  
  general:
    value: NEUTRAL
    historical-fitness: +5%
    recommendation: Include when frontend needed
---

# React Skill

## Capability Injection

```
You have deep React expertise:

COMPONENTS
- Prefer functional components with hooks
- Single responsibility - one component, one job
- Extract custom hooks for reusable logic
- Props down, events up

STATE MANAGEMENT
- Start local (useState)
- Lift when sharing between siblings
- Context for deep prop drilling
- External store (Redux, Zustand) for complex global state

HOOKS
- useState for local state
- useEffect for side effects (careful with deps!)
- useMemo for expensive computations
- useCallback for stable function references
- useRef for DOM access and persistence without re-render

PATTERNS
- Composition over inheritance
- Render props for behavior sharing
- Compound components for flexible APIs
- Container/Presentational when appropriate

PERFORMANCE
- React.memo for pure components
- Avoid inline function definitions in JSX
- Virtualize long lists
- Profile before optimizing
```

## Contextual Value

### creative: +28%
Great for innovative UI patterns and designs.

### prototyping: +22%
Fast component iteration.

## Synergies

- **+ creative:** Innovative UI patterns
- **+ methodical:** Consistent component structure
- **+ testing:** Component testing with React Testing Library
- **+ defensive:** Error boundaries, loading states

## Tools Granted

Read, Write, Edit, Bash (dev server, builds, tests)

## Self-Modification Triggers

REDUCE when: Backend-only work, no UI needed
INCREASE when: UI-heavy project, component library work
