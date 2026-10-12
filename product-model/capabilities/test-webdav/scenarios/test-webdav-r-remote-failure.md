---
{
  "kind": "edge",
  "routes": {
    "main": "R remote failure"
  },
  "steps": [
    {
      "text": "Request remote connectivity verification.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
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
          "place": "console::administration::webdav"
        }
      }
    },
    {
      "text": "Save changes to the WebDAV settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "webdav-settings",
          "effect": "changes",
          "facts": [
            "Last result"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The distinguished remote failure is returned and applicable last-result information retained; success is not fabricated.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
        }
      },
      "actor": "owner"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Exchange.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/SetupWizard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/exchange.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/exchange/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/webdav.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/webdavsync/service.go"
    }
  ]
}
---








# Test webdav remote failure

## Trigger

The configured remote check-in, key or WebDAV operation fails.

## Outcome

The distinguished remote failure is returned and applicable last-result information retained; success is not fabricated.
