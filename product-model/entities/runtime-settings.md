---
{
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
  ],
  "domain": "runtime-settings",
  "singleton": true
}
---



# Runtime settings

The Product-wide supported effective runtime configuration and its stored overrides.

## Information kept

- **Editable values** — the supported runtime values accepting an override.
- **Effective values** — the currently resolved values after defaults, environment and stored overrides.
- **Sources** — the origin of each resolved runtime value.
- **Override** — the persisted runtime override, absent after reset.
