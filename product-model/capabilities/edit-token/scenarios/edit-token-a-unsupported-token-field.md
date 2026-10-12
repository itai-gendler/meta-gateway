---
{
  "kind": "validation",
  "routes": {
    "main": "A unsupported token field"
  },
  "steps": [
    {
      "text": "Supply replacement credential settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-tokens"
        }
      },
      "actor": "member"
    },
    {
      "text": "The own-field request includes ownership, scope, group, denylist or budget/counter settings outside the strict DTO.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-tokens"
        }
      }
    },
    {
      "text": "Strict decoding rejects the unsupported fieldset without saving privileged changes.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-tokens"
        }
      },
      "actor": "member"
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









# Edit token unsupported token field

## Trigger

The own-field request includes ownership, scope, group, denylist or budget/counter settings outside the strict DTO.

## Outcome

Strict decoding rejects the unsupported fieldset without saving privileged changes.
