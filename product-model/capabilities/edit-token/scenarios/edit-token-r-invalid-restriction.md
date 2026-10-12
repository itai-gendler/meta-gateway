---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid restriction"
  },
  "steps": [
    {
      "text": "Supply replacement credential settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The Token model/IP/scope/expiry restriction input is invalid for its contract.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
        }
      }
    },
    {
      "text": "The Token input is rejected rather than weakening its restrictions.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
        }
      },
      "actor": "owner"
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








# Edit token invalid restriction

## Trigger

The Token model/IP/scope/expiry restriction input is invalid for its contract.

## Outcome

The Token input is rejected rather than weakening its restrictions.
