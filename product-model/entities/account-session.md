---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/AccountPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go#redeemCredit"
    }
  ],
  "domain": "account"
}
---



# Account session

A listed browser session bound to an Account and its security revision.

## Information kept

- **Account** — the associated Account, without implying current credential eligibility.
- **Created at** — the time the Product established this record.
- **Expires at** — the instant after which the session credential ceases to be valid.
- **Session credential** — protected session authority presented by the browser.
- **Session revision** — the Account security revision used to invalidate previously established sessions.
- **Current session** — whether the listed session is the browser session making the request.
