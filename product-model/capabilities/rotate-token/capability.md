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



# Rotate token

Replace a selected Token credential and invalidate its previous cached authority.

New plaintext authority is returned and the previous credential no longer authenticates through this operation.
