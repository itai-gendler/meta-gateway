---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid settings"
  },
  "steps": [
    {
      "text": "Supply supported override values.",
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
      "text": "The submitted routing or runtime values fail supported validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::runtime-settings"
        }
      }
    },
    {
      "text": "The settings are rejected and the previous valid configuration remains.",
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








# Change runtime settings invalid settings

## Trigger

The submitted routing or runtime values fail supported validation.

## Outcome

The settings are rejected and the previous valid configuration remains.
