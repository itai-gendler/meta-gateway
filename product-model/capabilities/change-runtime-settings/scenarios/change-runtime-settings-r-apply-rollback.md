---
{
  "kind": "edge",
  "routes": {
    "main": "R apply rollback"
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
      "text": "A supported runtime override persists but applying it fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::runtime-settings"
        }
      }
    },
    {
      "text": "The previous persisted/effective state is restored and the apply failure returned.",
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








# Change runtime settings apply rollback

## Trigger

A supported runtime override persists but applying it fails.

## Outcome

The previous persisted/effective state is restored and the apply failure returned.
