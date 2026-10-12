---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ],
  "domain": "account",
  "relations": [
    {
      "entity": "account-session",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "account-token",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "routing-plan",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "third-party-identity",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "usage-record",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "request-log-entry",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---



# Account

Personal and security information retained independently of the fixed role currently held.

## Information kept

- **Login name** — the normalized sign-in name, unique against existing Accounts and the reserved operator name.
- **Display name** — the human-facing name retained for the Account.
- **Status** — the Active or Paused Account choice checked by current Team access.
- **Password credential** — protected password authority; a replacement is supplied without disclosing the stored password hash.
- **Policy** — the selected access policy governing the Account or invitation assignment.
- **Token limit** — the Account token-usage budget; zero means unlimited.
- **Tokens used** — the accumulated recorded token usage, retained until an explicit counter reset.
- **Money limit** — the configured monetary budget in the gateway ledger unit; zero means unlimited.
- **Money used** — the accumulated recorded configured cost in the gateway ledger unit.
- **Request preferences** — failover inheritance/on/off and optional retry cap, applied only while the policy allows editing.
- **Token count** — the count of retained non-neutralized Account tokens, including disabled tokens.
- **Session revision** — the Account security revision used to invalidate previously established sessions.

## States

### Active

The Account is active for applicable team access.

### Paused

The Account is paused and fails applicable team access.
