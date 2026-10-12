---
{
  "kind": "primary",
  "routes": {
    "main": "R scheduled run"
  },
  "steps": [
    {
      "text": "The configured schedule is due.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
        }
      },
      "unattended": true
    },
    {
      "text": "Consult the WebDAV settings. Consult the Connection. Consult the Upstream API key. Consult the Upstream account.",
      "kind": "condition",
      "entities": [
        {
          "entity": "webdav-settings",
          "effect": "reads",
          "facts": [
            "Upload connection",
            "Credential availability",
            "Direction enablement",
            "Schedules"
          ]
        },
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Name",
            "Site",
            "Credential association",
            "Base address",
            "Protocol",
            "Status",
            "Priority",
            "Weight",
            "Model snapshot",
            "Model sync mode",
            "Routing controls",
            "Forwarding settings",
            "Connectivity observations"
          ]
        },
        {
          "entity": "upstream-api-key",
          "effect": "reads",
          "facts": [
            "Credential"
          ]
        },
        {
          "entity": "upstream-account",
          "effect": "reads",
          "facts": [
            "Credential",
            "Cookie"
          ]
        }
      ],
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
      }
    },
    {
      "text": "The remote document and direction result are updated while protected other formats are not overwritten; service export includes configured secrets.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::webdav"
        }
      }
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








# Upload webdav scheduled run

## Trigger

The configured schedule becomes due for upload the canonical connection representation through the configured upload direction.

## Outcome

The remote document and direction result are updated while protected other formats are not overwritten; service export includes configured secrets.
