---
{
  "kind": "edge",
  "routes": {
    "main": "R plaintext unavailable"
  },
  "steps": [
    {
      "text": "Select the Token secret reveal.",
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
      "text": "The retained Token authenticates through its hash but has no decryptable saved plaintext.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::tokens"
        }
      }
    },
    {
      "text": "Reveal returns its conflict/unavailable result; valid caller-held authority is not declared invalid merely because reveal fails.",
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








# Reveal token plaintext unavailable

## Trigger

The retained Token authenticates through its hash but has no decryptable saved plaintext.

## Outcome

Reveal returns its conflict/unavailable result; valid caller-held authority is not declared invalid merely because reveal fails.
