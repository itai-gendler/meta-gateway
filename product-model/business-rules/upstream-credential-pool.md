---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "capability",
      "id": "refresh-connection-models"
    },
    {
      "type": "capability",
      "id": "check-upstream-account"
    },
    {
      "type": "entity",
      "id": "upstream-api-key"
    },
    {
      "type": "entity",
      "id": "upstream-account"
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



# Relay secret selection differs from Account operations and blank-model filtering fails open

Relay chooses enabled secret-bearing supported API/access/session credentials, consulting model restrictions/evidence, priorities, rotation and decryption. A blank-model fail-open fallback bypasses model filtering including explicit allowlists. Upstream Account operations separately resolve an enabled relevant Site/user credential, supported adapter, platform identity and decryptable secret or cookie; they do not simply require the Connection enabled choice. Cookie-only Account authority is insufficient for a secret-bearing relay key.
