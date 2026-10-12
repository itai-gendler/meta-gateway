---
{
  "entities": [
    {
      "entity": "account-token",
      "shows": [
        "Name",
        "Credential",
        "Credential hint",
        "Status",
        "Model restrictions",
        "IP restrictions",
        "Expiry",
        "Tokens used",
        "Account"
      ],
      "collects": [
        "Name",
        "Model restrictions",
        "Expiry",
        "IP restrictions",
        "Status"
      ]
    },
    {
      "entity": "usage-record",
      "shows": [
        "Recorded cost"
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




# Own tokens

The owned downstream credential subject presents retained access settings and explicit reveal/rotation outcomes.
