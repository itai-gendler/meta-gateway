---
{
  "kind": "primary",
  "routes": {
    "main": "S connection tested"
  },
  "steps": [
    {
      "text": "Request remote connectivity verification.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
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
          "place": "console::administration::setup"
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
            "Download connection",
            "Credential availability",
            "Direction enablement",
            "Schedules",
            "Last result"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The remote test result is returned; Setup first saves its supplied download settings with schedules off. Setup persists the supplied download settings, enables download, disables upload and leaves schedules off.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
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

The remote test result is returned; Setup first saves its supplied download settings with schedules off. Setup persists the supplied download settings, enables download, disables upload and leaves schedules off.
