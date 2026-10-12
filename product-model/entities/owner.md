---
{
  "acts": "external",
  "kind": "person",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/session.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/session.go#login"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_oauth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team.go"
    }
  ],
  "relations": [
    {
      "entity": "account",
      "verb": "owns",
      "cardinality": "one-to-one"
    }
  ]
}
---



# Owner

The person holding the gateway Owner role, responsible for full gateway and team administration and their own Account security.

## Information kept

- **Account association** — the Account for which this person currently holds this fixed Product role; establishing or dropping the association changes the role held, not the human.
