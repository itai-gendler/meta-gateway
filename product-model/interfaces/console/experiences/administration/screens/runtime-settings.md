---
{
  "entities": [
    {
      "entity": "runtime-settings",
      "shows": [
        "Editable values",
        "Effective values",
        "Sources",
        "Override"
      ],
      "collects": [
        "Editable values",
        "Override"
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



# Runtime settings

The effective runtime configuration subject shows values, sources and stored overrides.
