---
{
  "kind": "primary",
  "routes": {
    "main": "R environment restored"
  },
  "steps": [
    {
      "text": "Reset runtime overrides.",
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
      "text": "Save changes to the Runtime settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "runtime-settings",
          "effect": "changes",
          "facts": [
            "Override",
            "Effective values",
            "Sources"
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
      "text": "The override is absent and effective values resolve from environment/default sources.",
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








# Reset runtime settings environment restored

## Trigger

Reset runtime overrides.

## Outcome

The override is absent and effective values resolve from environment/default sources.
