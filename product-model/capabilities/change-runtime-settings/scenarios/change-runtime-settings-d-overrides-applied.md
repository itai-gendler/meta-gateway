---
{
  "kind": "primary",
  "routes": {
    "main": "D overrides applied"
  },
  "steps": [
    {
      "text": "Supply supported override values.",
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
      "text": "Save changes to the Runtime settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "runtime-settings",
          "effect": "changes",
          "facts": [
            "Editable values",
            "Override",
            "Effective values",
            "Sources"
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
      "text": "The override and effective values change only after successful application; failed application is rolled back.",
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








# Change runtime settings overrides applied

## Trigger

Supply supported override values.

## Outcome

The override and effective values change only after successful application; failed application is rolled back.
