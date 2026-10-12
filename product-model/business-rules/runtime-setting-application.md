---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-runtime-settings"
    },
    {
      "type": "capability",
      "id": "reset-runtime-settings"
    },
    {
      "type": "entity",
      "id": "runtime-settings"
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



# Runtime application failure rolls back persisted and effective values

Validate/persist/apply; apply failure rolls back; reset clears overrides and restores environment-derived effective values
