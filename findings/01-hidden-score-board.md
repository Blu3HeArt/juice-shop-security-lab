# Finding 01: Discoverable Hidden Score Board Route

## Classification

- Severity: Informational
- Category: Content discovery
- Target: OWASP Juice Shop local lab
- Status: Confirmed

## Summary

The Juice Shop Score Board was not linked through the visible navigation menu, but its existence was disclosed through an API response. The application's client-side routing pattern made it possible to infer and access the hidden route.

## Evidence

Observed API request:

`GET /api/Challenges/?name=Score%20Board`

Important response fields:

- Name: Score Board
- Description: Find the carefully hidden Score Board page.
- Difficulty: 1
- Solved: false

Inferred route:

`http://localhost:3000/#/score-board`

The route successfully displayed the Score Board page.

## Reproduction Steps

1. Open OWASP Juice Shop.
2. Open Firefox Developer Tools.
3. Select the Network tab.
4. Reload the application.
5. Inspect the request for `/api/Challenges/?name=Score Board`.
6. Observe that the response identifies a hidden Score Board page.
7. Identify the application's `/#/route-name` convention.
8. Navigate to `/#/score-board`.
9. Confirm that the Score Board appears.

## Security Impact

The Score Board does not contain sensitive information, so this observation is informational. However, a real application could expose sensitive functionality if it relied only on removing links from its navigation menu.

Hidden routes should not be treated as protected routes.

## Recommendation

Sensitive routes should enforce server-side authentication and authorization. Removing a link from the interface should never be the only security control.

## Lab Note

This behavior is intentional in OWASP Juice Shop and is included for security training.
