---
skill: testing
type: domain
default-weight: 0.6

provides-tools: [Read, Write, Edit, Bash]
synergizes-with: [analytical, defensive, methodical]

# THIS IS A SAFETY SKILL
safety-skill: true
critical-for: [aggressive, experimental]

contextual-value:
  security-critical:
    value: ESSENTIAL
    historical-fitness: +35%
    minimum-weight: 0.6
    recommendation: REQUIRE
  
  prototyping:
    value: MODERATE
    historical-fitness: +8%
    recommendation: Include at 0.4 for safety
  
  general:
    value: BENEFICIAL
    historical-fitness: +25%
    recommendation: DEFAULT INCLUDE

balances:
  aggressive:
    when-above: 0.5
    minimum-testing: 0.5
    reason: Fast iteration needs test safety net
  experimental:
    when-above: 0.5
    minimum-testing: 0.4
    reason: Experiments need verification
---

# Testing Skill

## Capability Injection

```
You have deep testing expertise:

TEST PHILOSOPHY
- Tests document expected behavior
- Write test BEFORE fixing bug (captures it)
- Test behavior, not implementation
- Coverage is guidance, not gospel

UNIT TESTS
- One assertion focus per test
- Descriptive names: should_do_X_when_Y
- Arrange-Act-Assert pattern
- Mock external dependencies only

INTEGRATION TESTS
- Test component interactions
- Use real dependencies when practical
- Focus on critical paths
- Balance coverage vs speed

TEST DESIGN
- Happy path first
- Then edge cases (null, empty, huge, negative)
- Then error conditions
- Prioritize by risk

ANTI-GAMING
- Never write trivial tests (assert true)
- Never delete failing tests to pass
- Tests must actually exercise code
- Coverage without assertions is worthless
```

## CRITICAL: Safety Net Role

This skill PREVENTS fitness crashes when combined with risky traits:

**aggressive > 0.5 REQUIRES testing >= 0.5**
- Without: 73% failure rate
- With: 22% failure rate

**experimental > 0.5 REQUIRES testing >= 0.4**
- Without: 68% failure rate  
- With: 18% failure rate

## Contextual Value

### security-critical: ESSENTIAL
+35% fitness. REQUIRE >= 0.6. Tests catch security regressions.

### prototyping: MODERATE
+8% fitness. Include at 0.4 minimum for safety net.

## Tools Granted

Read, Write, Edit, Bash (for running tests)

## Gaming Detection

This skill helps FLUX detect gaming:
- Tests pass but coverage < 20%? → FLAG
- All tests trivial (no real assertions)? → FLAG
- Tests deleted to make suite pass? → FLAG

## Self-Modification Triggers

REDUCE when: throwaway prototype, exploring only
INCREASE when: errors recurring, production code, aggressive/experimental present
