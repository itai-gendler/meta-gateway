---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-request-preferences"
    },
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "capability",
      "id": "send-message"
    },
    {
      "type": "entity",
      "id": "account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/AccountPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go#redeemCredit"
    }
  ]
}
---



# Granted request preferences only narrow regular Account-token forwarding

Granted preferences narrow regular failover/retry behavior; no blanket inheritance by diagnostic execution
