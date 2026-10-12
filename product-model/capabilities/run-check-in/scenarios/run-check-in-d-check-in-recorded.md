---
{
  "kind": "primary",
  "routes": {
    "main": "D check in recorded"
  },
  "steps": [
    {
      "text": "Request or schedule native check-in.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Upstream account. Consult the Site. Consult the Runtime settings.",
      "kind": "condition",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "reads",
          "facts": [
            "Site",
            "Credential",
            "Cookie",
            "Credential availability",
            "Authentication mode",
            "Platform identity",
            "Status",
            "Check-in setting"
          ]
        },
        {
          "entity": "site",
          "effect": "reads",
          "facts": [
            "Platform",
            "Status"
          ]
        },
        {
          "entity": "runtime-settings",
          "effect": "reads",
          "facts": [
            "Effective values"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the Upstream account.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Account observations"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The observed success/failure/reward is recorded; concurrent runs for the same credential are serialized.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Checkins.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/checkin.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/checkin/service.go"
    }
  ]
}
---








# Run check in check in recorded

## Trigger

Request or schedule native check-in.

## Outcome

The observed success/failure/reward is recorded; concurrent runs for the same credential are serialized.
