---
{
  "kind": "primary",
  "routes": {
    "main": "D display saved"
  },
  "steps": [
    {
      "text": "Supply symbol and valid display rate.",
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
      "text": "Save changes to the Money display settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "money-display-settings",
          "effect": "changes",
          "facts": [
            "Symbol",
            "Rate"
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
      "text": "Display settings change without repricing persisted costs.",
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
      "target": "web/src/features/ops/RuntimeSettingsPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/runtime_settings.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/display_settings.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/runtimeconfig/runtimeconfig.go"
    }
  ]
}
---








# Change money display display saved

## Trigger

Supply symbol and valid display rate.

## Outcome

Display settings change without repricing persisted costs.
