---
{
  "kind": "primary",
  "routes": {
    "main": "A preferences saved"
  },
  "steps": [
    {
      "text": "Supply failover and retry choices.",
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
      "text": "Consult the Access policy.",
      "kind": "condition",
      "entities": [
        {
          "entity": "access-policy",
          "effect": "reads",
          "facts": [
            "Request preference editing"
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
      "text": "Save changes to the Account.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Request preferences"
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
      "text": "The saved preferences narrow applicable regular local profile-token forwarding.",
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








# Change request preferences preferences saved

## Trigger

Supply failover and retry choices.

## Outcome

The saved preferences narrow applicable regular Account-token forwarding.
