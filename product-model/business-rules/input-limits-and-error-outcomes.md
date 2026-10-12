---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-account"
    },
    {
      "type": "capability",
      "id": "import-accounts"
    },
    {
      "type": "capability",
      "id": "adjust-account-quota"
    },
    {
      "type": "capability",
      "id": "create-code"
    },
    {
      "type": "capability",
      "id": "create-connection"
    },
    {
      "type": "capability",
      "id": "edit-connection"
    },
    {
      "type": "capability",
      "id": "create-credential"
    },
    {
      "type": "capability",
      "id": "edit-credential"
    },
    {
      "type": "capability",
      "id": "test-connection-model"
    },
    {
      "type": "capability",
      "id": "change-connection-model-alias"
    },
    {
      "type": "capability",
      "id": "create-route"
    },
    {
      "type": "capability",
      "id": "edit-route"
    },
    {
      "type": "capability",
      "id": "add-route-member"
    },
    {
      "type": "capability",
      "id": "edit-route-member"
    },
    {
      "type": "capability",
      "id": "rename-route-group"
    },
    {
      "type": "capability",
      "id": "copy-route-group"
    },
    {
      "type": "capability",
      "id": "edit-model-metadata"
    },
    {
      "type": "capability",
      "id": "create-billing-multiplier"
    },
    {
      "type": "capability",
      "id": "edit-billing-multiplier"
    },
    {
      "type": "capability",
      "id": "create-token-group"
    },
    {
      "type": "capability",
      "id": "edit-token-group"
    },
    {
      "type": "capability",
      "id": "create-token"
    },
    {
      "type": "capability",
      "id": "edit-token"
    },
    {
      "type": "capability",
      "id": "create-routing-plan"
    },
    {
      "type": "capability",
      "id": "generate-image"
    },
    {
      "type": "capability",
      "id": "probe-image-generation"
    },
    {
      "type": "capability",
      "id": "vary-image"
    },
    {
      "type": "capability",
      "id": "change-check-in-settings"
    },
    {
      "type": "capability",
      "id": "import-connections"
    },
    {
      "type": "capability",
      "id": "change-webdav-settings"
    },
    {
      "type": "capability",
      "id": "change-runtime-settings"
    },
    {
      "type": "capability",
      "id": "change-money-display"
    },
    {
      "type": "capability",
      "id": "restore-backup"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/relay.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_health.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_keypool.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/usage.go"
    }
  ]
}
---



# Mapped invalid inputs and oversized bodies retain distinguished failure outcomes

The mapped operations reject their specified invalid fieldsets, bounds and shapes instead of silently weakening guards. Staff Account/import/bulk requests preserve supported bounds: display name 80 characters, imported or selected rows at most 500, import material at most 64 KiB, Account token totals up to 10^12 and monetary totals up to 10^6. Policies validate names, rate/count bounds and current unique member identities. Relay body defaults are 32 MiB chat and 64 MiB images and can be configured; oversize returns the distinguished body-limit outcome. Partial item import and connection save before later verification remain separate outcomes.
