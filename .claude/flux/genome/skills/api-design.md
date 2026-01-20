---
skill: api-design
type: domain
default-weight: 0.7

provides-tools: [Read, Write, Edit, Bash, WebFetch]
synergizes-with: [analytical, methodical, defensive]

contextual-value:
  security-critical:
    value: ESSENTIAL
    historical-fitness: +32%
    minimum-weight: 0.7
    recommendation: REQUIRE for auth/payment APIs
  
  performance:
    value: BENEFICIAL
    historical-fitness: +18%
    recommendation: For optimized endpoints
  
  general:
    value: BENEFICIAL
    historical-fitness: +20%
    recommendation: INCLUDE for backend work
---

# API Design Skill

## Capability Injection

```
You have deep API design expertise:

REST PRINCIPLES
- Resources are nouns: /users, /orders, /products
- HTTP verbs for actions: GET read, POST create, PUT replace, PATCH update, DELETE remove
- Status codes matter: 200 OK, 201 Created, 400 Bad Request, 401 Unauthorized, 404 Not Found, 500 Server Error

ENDPOINT DESIGN
- Consistent naming: /users/{id}/orders not /getUserOrders
- Plural nouns for collections
- Nested resources for relationships
- Query params for filtering, sorting, pagination

VERSIONING
- URL versioning: /v1/users
- Or header: Accept: application/vnd.api+json;version=1
- Never break existing versions

ERROR HANDLING
- Consistent error format across all endpoints
- Meaningful messages for developers
- Error codes for programmatic handling
- Never expose internal stack traces

SECURITY
- HTTPS always, no exceptions
- Authentication: Bearer tokens, API keys
- Authorization: Check permissions on every request
- Rate limiting per client
- Input validation on EVERYTHING
- Never trust client data

DOCUMENTATION
- OpenAPI/Swagger spec
- Examples for every endpoint
- List all error conditions
- Keep docs with code
```

## Contextual Value

### security-critical: ESSENTIAL
+32% fitness. Proper API design prevents security holes.

### general: BENEFICIAL
+20% fitness. Good APIs enable good systems.

## Synergies

- **+ analytical:** Well-structured API hierarchy
- **+ methodical:** Consistent conventions
- **+ defensive:** Robust error handling
- **+ testing:** Comprehensive API tests

## Tools Granted

Read, Write, Edit, Bash, WebFetch (for testing external APIs)

## Gaming Detection

Poor API design indicators:
- Inconsistent naming → -10 fitness
- Missing error handling → -15 fitness
- No input validation → -30 fitness (security critical!)
- Exposed internal errors → -20 fitness

## Self-Modification Triggers

REDUCE when: Frontend-only, no API work
INCREASE when: Building APIs, authentication, security context
