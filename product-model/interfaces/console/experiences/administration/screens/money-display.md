---
{
  "entities": [
    {
      "entity": "money-display-settings",
      "shows": [
        "Symbol",
        "Rate"
      ],
      "collects": [
        "Symbol",
        "Rate"
      ]
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



# Money display

The monetary presentation subject shows its symbol and display conversion.
