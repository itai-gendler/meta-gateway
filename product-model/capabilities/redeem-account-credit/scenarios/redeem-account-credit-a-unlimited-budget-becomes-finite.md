---
{
  "kind": "edge",
  "routes": {
    "main": "A unlimited budget becomes finite"
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
      "text": "A credit face value is redeemed into a zero, unlimited total with retained prior usage.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      }
    },
    {
      "text": "Save changes to the Credit code. Save changes to the Account.",
      "kind": "product",
      "entities": [
        {
          "entity": "credit-code",
          "effect": "changes",
          "facts": [
            "Uses",
            "Redemptions"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Token limit",
            "Money limit"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::account"
        }
      },
      "actor": "member"
    },
    {
      "text": "The total becomes that finite positive amount; counters remain, so the resulting finite pool can already be exhausted.",
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








# Redeem account credit unlimited budget becomes finite

## Trigger

A credit face value is redeemed into a zero, unlimited total with retained prior usage.

## Outcome

The total becomes that finite positive amount; counters remain, so the resulting finite pool can already be exhausted.
