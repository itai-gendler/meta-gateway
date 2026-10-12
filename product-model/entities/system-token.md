---
{
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
  ],
  "domain": "tokens",
  "relations": [
    {
      "entity": "usage-record",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "request-log-entry",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "live-request",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---



# System token

A staff-created downstream credential independent of a team Account policy.

## Information kept

- **Name** — the privileged downstream Token's display name.
- **Credential** — the downstream bearer authority and its protected stored representation; custom hash-only authority may lack revealable plaintext.
- **Credential hint** — a non-secret display hint identifying a Token.
- **Status** — the Enabled or Disabled choice checked on authentication.
- **Scopes** — the Token endpoint permissions, normalized according to its credential contract.
- **Model restrictions** — the configured model-name allowlist or restrictions for this credential.
- **Denylist** — the configured downstream model exclusions.
- **IP restrictions** — the permitted caller addresses or networks.
- **Expiry** — the configured Token expiry, checked at admission.
- **Token group** — the quota/rate group selected by the Token.
- **Route group** — the routing-member group selected by the Token.
- **Token limit** — this credential token-usage budget; zero means unlimited.
- **Tokens used** — the accumulated recorded token usage, retained until an explicit counter reset.
- **Money limit** — the configured monetary budget in the gateway ledger unit; zero means unlimited.
- **Money used** — the accumulated recorded configured cost in the gateway ledger unit.

## States

### Enabled

The saved enabled choice permits consideration by the applicable admission or selection rules.

### Disabled

The saved disabled choice excludes ordinary admission or selection.
