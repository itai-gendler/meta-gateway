---
{
  "kind": "validation",
  "routes": {
    "main": "A unusable credit"
  },
  "steps": [
    {
      "text": "Supply the credit credential.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    },
    {
      "text": "The presented credit authority is missing, revoked, expired or globally exhausted.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      }
    },
    {
      "text": "Redemption is refused without incrementing use or changing totals.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    }
  ],
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








# Redeem account credit unusable credit

## Trigger

The presented credit authority is missing, revoked, expired or globally exhausted.

## Outcome

Redemption is refused without incrementing use or changing totals.
