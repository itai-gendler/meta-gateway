---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "capability",
      "id": "call-completions"
    },
    {
      "type": "capability",
      "id": "call-responses"
    },
    {
      "type": "capability",
      "id": "call-messages"
    },
    {
      "type": "capability",
      "id": "create-embedding"
    },
    {
      "type": "capability",
      "id": "count-message-tokens"
    },
    {
      "type": "capability",
      "id": "generate-image"
    },
    {
      "type": "capability",
      "id": "edit-image"
    },
    {
      "type": "capability",
      "id": "vary-image"
    },
    {
      "type": "capability",
      "id": "browse-models"
    },
    {
      "type": "capability",
      "id": "read-token-credit"
    },
    {
      "type": "entity",
      "id": "system-token"
    },
    {
      "type": "entity",
      "id": "account-token"
    },
    {
      "type": "entity",
      "id": "access-policy"
    },
    {
      "type": "entity",
      "id": "token-group"
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



# Inference admission applies current credential, policy and simultaneous budget checks

The resolved credential snapshot must pass enabled/non-neutralized, expiry and IP admission. Applicable endpoint scopes and model restrictions, the current linked active Account in Team mode, its current policy model/member grants, rates and all positive Token/group/Account token and money budgets are checked. Empty scopes default to relay. Malformed historical System-token scopes have relay fallback; malformed Account-token scopes reject. Missing group definitions supply no group limit. Checks occur before execution without reservation or a promised final-charge ceiling. Credit reading authenticates its presented Token and reports only that Token's budgets outside endpoint-scope/quota checks.
