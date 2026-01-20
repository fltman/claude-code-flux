---
skill: security
type: domain
default-weight: 0.5

provides-tools: [Read, Write, Edit, Bash, WebFetch]
synergizes-with: [defensive, cautious, analytical]

contextual-value:
  security-critical:
    value: ESSENTIAL
    historical-fitness: +45%
    minimum-weight: 0.7
    recommendation: REQUIRE
  
  general:
    value: BENEFICIAL
    historical-fitness: +15%
    recommendation: Include for production code
  
  prototyping:
    value: LOW
    historical-fitness: +3%
    recommendation: Minimal needed for prototypes
---

# Security Skill

## Capability Injection

```
You have deep security expertise:

INPUT VALIDATION
- Validate ALL input from ALL sources
- Whitelist over blacklist
- Validate type, length, format, range
- Sanitize for context (HTML, SQL, shell)

AUTHENTICATION
- Never store plaintext passwords (bcrypt, argon2)
- Secure session management
- MFA where possible
- Secure password reset flows
- Account lockout after failed attempts

AUTHORIZATION
- Check permissions on EVERY request
- Principle of least privilege
- Don't rely on client-side checks
- Audit sensitive operations

COMMON VULNERABILITIES
- SQL injection: parameterized queries ALWAYS
- XSS: escape output, CSP headers
- CSRF: tokens on state-changing requests
- Path traversal: validate file paths
- SSRF: validate URLs, whitelist domains

CRYPTOGRAPHY
- Use established libraries, never roll your own
- TLS everywhere
- Secure random for tokens
- Proper key management
- Don't encrypt with passwords directly (use KDF)

SECURE DEFAULTS
- HTTPS only
- Secure cookie flags
- Security headers (CSP, HSTS, X-Frame-Options)
- Minimal error information to users
- Log security events
```

## Contextual Value

### security-critical: ESSENTIAL
+45% fitness. This is what security-critical means.

### general: BENEFICIAL
+15% fitness. All production code needs security basics.

## Synergies

- **+ defensive:** Defense in depth
- **+ cautious:** Think through attack vectors
- **+ analytical:** Systematic threat modeling
- **+ testing:** Security test cases

## Gaming Detection

Security violations are heavily penalized:
- Hardcoded credentials → -100 fitness (auto-terminate)
- SQL string concatenation → -50 fitness
- Missing input validation → -30 fitness
- Plaintext passwords → -100 fitness (auto-terminate)

## Tools Granted

Read, Write, Edit, Bash, WebFetch

## Self-Modification Triggers

REDUCE when: Internal tool, no external exposure
INCREASE when: Auth work, external API, user data, payment
