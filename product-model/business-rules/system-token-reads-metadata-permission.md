---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "system-token",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "inference-api"
        }
      ],
      "facts": [
        "Name",
        "Credential hint",
        "Status",
        "Scopes",
        "Model restrictions",
        "Denylist",
        "IP restrictions",
        "Expiry",
        "Token group",
        "Route group",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "configuredBy": "system-token",
      "actors": [
        "gateway-client"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Keys.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_keys.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/downstream_key.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    }
  ]
}
---



# Deployment administrator, Owner or Gateway client using System token may read System token

Deployment administrator and Owner create, configure, reveal, rotate or physically delete System tokens. Inference uses the actual presented credential for its supported credit or relay contract after that contract's checks. Credit reporting and relay admission retain their distinct scope/quota boundaries.
