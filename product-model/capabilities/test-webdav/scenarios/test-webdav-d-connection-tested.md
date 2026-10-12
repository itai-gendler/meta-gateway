---
{
  "kind": "primary",
  "routes": {
    "main": "D connection tested"
  },
  "steps": [
    {
      "text": "Request remote connectivity verification.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the WebDAV settings.",
      "kind": "condition",
      "entities": [
        {
          "entity": "webdav-settings",
          "effect": "reads",
          "facts": [
            "Download connection",
            "Upload connection",
            "Credential availability"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The remote test result is returned; Setup first saves its supplied download settings with schedules off.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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








# Test webdav connection tested

## Trigger

Request remote connectivity verification.

## Outcome

The configured direction is tested and its observed remote result is remembered.
