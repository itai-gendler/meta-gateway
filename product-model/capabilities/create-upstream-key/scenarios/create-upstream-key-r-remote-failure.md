---
{
  "kind": "edge",
  "routes": {
    "main": "R remote failure"
  },
  "steps": [
    {
      "text": "Supply the supported remote-key creation choice.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The configured remote check-in, key or WebDAV operation fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "The distinguished remote failure is returned and applicable last-result information retained; success is not fabricated.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Channels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/ChannelModels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_connections.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_credentials.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/discovery.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go#CreateKey"
    }
  ]
}
---











# Create upstream key remote failure

## Trigger

The configured remote check-in, key or WebDAV operation fails.

## Outcome

The distinguished remote failure is returned and applicable last-result information retained; success is not fabricated.

## Edge cases

- A remote key can already exist when its secret remains masked or a subsequent local write fails. Return the classified failure, including token_created_but_secret_masked where applicable; do not claim rollback of remote creation or earlier successful local writes.
