---
{
  "kind": "validation",
  "routes": {
    "main": "A foreign token"
  },
  "steps": [
    {
      "text": "Select credential rotation.",
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
      "text": "The selected retained Token belongs to another local profile or is not available through the owned boundary.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::own-tokens"
        }
      }
    },
    {
      "text": "The operation returns its not-found/refusal result and the foreign credential/settings remain undisclosed or unchanged.",
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








# Rotate token foreign token

## Trigger

The selected retained Token belongs to another Account or is not available through the owned boundary.

## Outcome

The operation returns its not-found/refusal result and the foreign credential/settings remain undisclosed or unchanged.
