---
{
  "kind": "primary",
  "routes": {
    "main": "D schedule saved"
  },
  "steps": [
    {
      "text": "Supply check-in enablement and schedule choices.",
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
      "text": "Save changes to the Upstream account. Save changes to the Runtime settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Check-in setting"
          ]
        },
        {
          "entity": "runtime-settings",
          "effect": "changes",
          "facts": [
            "Editable values",
            "Override"
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
      "text": "Supported credential and runtime configuration are saved for future manual/scheduled runs.",
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








# Change check in settings schedule saved

## Trigger

Supply check-in enablement and schedule choices.

## Outcome

Supported credential and runtime settings are saved for future manual/scheduled runs.
