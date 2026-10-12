---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "system-token",
      "effect": "changes",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ],
      "facts": [
        "Credential",
        "Credential hint",
        "Status"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
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



# Deployment administrator, Owner may change System token Credential, Credential hint, Status

Deployment administrator and Owner create, configure, reveal, rotate or physically delete System tokens. Inference uses the actual presented credential for its supported credit or relay contract after that contract's checks. Credit reporting and relay admission retain their distinct scope/quota boundaries.
