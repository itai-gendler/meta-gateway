---
{
  "kind": "primary",
  "routes": {
    "main": "A token saved"
  },
  "steps": [
    {
      "text": "Supply the name, model restrictions, expiry and allowed caller addresses.",
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
      "text": "Save changes to the Account token.",
      "kind": "product",
      "entities": [
        {
          "entity": "account-token",
          "effect": "changes",
          "facts": [
            "Name",
            "Model restrictions",
            "Expiry",
            "IP restrictions"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::own-tokens"
        }
      },
      "actor": "member"
    },
    {
      "text": "The allowed fields are saved; the personal contract rejects unsupported privileged fields.",
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









# Edit token token saved

## Trigger

Supply replacement credential settings.

## Outcome

The allowed fields are saved; the personal contract rejects unsupported privileged fields.

## Edge cases

- Invalid restrictions or unsupported privileged input fields are refused without a save. A foreign retained key is unavailable. The browser supplies name, model restrictions, expiry and caller-address restrictions; it does not supply plan selection or privileged budgets.
