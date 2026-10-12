---
{
  "kind": "primary",
  "routes": {
    "main": "R effective settings shown"
  },
  "steps": [
    {
      "text": "Read effective runtime configuration.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::runtime-settings"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Runtime settings.",
      "kind": "condition",
      "entities": [
        {
          "entity": "runtime-settings",
          "effect": "reads",
          "facts": [
            "Editable values",
            "Effective values",
            "Sources",
            "Override"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::runtime-settings"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Resolved values and environment/default/override sources are presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::runtime-settings"
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








# Browse runtime settings effective settings shown

## Trigger

Read effective runtime configuration.

## Outcome

Resolved values and environment/default/override sources are presented.
