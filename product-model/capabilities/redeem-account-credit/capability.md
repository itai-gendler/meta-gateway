---
{
  "availability": [
    {
      "place": "console::personal"
    }
  ],
  "domain": "account",
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
  ]
}
---



# Redeem account credit

Redeem a presented credit code into the current Account totals without resetting used counters.

The code use and this Account redemption are recorded atomically with face-value additions to token/money totals.
