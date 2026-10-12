---
{
  "kind": "primary",
  "routes": {
    "main": "A credit added"
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
      "text": "Consult the Credit code. Consult the Account.",
      "kind": "condition",
      "entities": [
        {
          "entity": "credit-code",
          "effect": "reads",
          "facts": [
            "Token grant",
            "Money grant",
            "Validity",
            "Use limit",
            "Uses",
            "Redemptions",
            "Revocation"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used"
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
      "text": "The code use and this local profile redemption are recorded atomically with face-value additions to token/money totals.",
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








# Redeem account credit credit added

## Trigger

Supply the credit credential.

## Outcome

The code use and this Account redemption are recorded atomically with face-value additions to token/money totals.
