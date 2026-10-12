---
{
  "availability": [
    {
      "place": "console::administration"
    },
    {
      "place": "console::personal"
    },
    {
      "place": "management-api::administration"
    }
  ],
  "domain": "tokens",
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
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "docs/reference/admin-api.md"
    }
  ]
}
---



# Disable token

Disable the selected retained Token.

The disabled state is saved and applicable authentication cache invalidated; disabled own Tokens still consume a creation slot.
