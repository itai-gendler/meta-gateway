---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid rate"
  },
  "steps": [
    {
      "text": "Supply symbol and valid display rate.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::money-display"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The monetary display rate is non-finite, nonpositive or outside the supported range.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::money-display"
        }
      }
    },
    {
      "text": "The display change is refused without rewriting saved ledger values.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::money-display"
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








# Change money display invalid rate

## Trigger

The monetary display rate is non-finite, nonpositive or outside the supported range.

## Outcome

The display change is refused without rewriting saved ledger values.
