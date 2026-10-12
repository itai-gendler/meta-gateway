---
{
  "kind": "primary",
  "routes": {
    "main": "R connections downloaded"
  },
  "steps": [
    {
      "text": "Request or schedule a download.",
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
      "text": "Consult the WebDAV settings.",
      "kind": "condition",
      "entities": [
        {
          "entity": "webdav-settings",
          "effect": "reads",
          "facts": [
            "Download connection",
            "Credential availability",
            "Direction enablement",
            "Schedules"
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
      "text": "Establish the Site. Establish the Upstream API key in Enabled state. Establish the Connection in Enabled state. Save changes to the WebDAV settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "site",
          "effect": "creates",
          "facts": [
            "Name",
            "Base address",
            "Platform",
            "Status",
            "Call policy"
          ]
        },
        {
          "entity": "upstream-api-key",
          "effect": "creates",
          "facts": [
            "Site",
            "Credential",
            "Secret availability",
            "Status",
            "Model restrictions",
            "Priority",
            "Discovery evidence",
            "Remote token reference"
          ],
          "to": "Enabled",
          "with": "site"
        },
        {
          "entity": "connection",
          "effect": "creates",
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
            "Connectivity observations",
            "Group name"
          ],
          "to": "Enabled",
          "with": "site"
        },
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
      "text": "Supported remote items are imported and the direction result retained; a disabled direction produces a skipped result.",
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








# Download webdav connections downloaded

## Trigger

Request or schedule a download.

## Outcome

Supported remote items are imported and the direction result retained; a disabled direction produces a skipped result.
