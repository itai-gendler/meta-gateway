---
{
  "availability": [
    {
      "place": "console::administration"
    },
    {
      "place": "management-api::administration"
    }
  ],
  "domain": "exchange",
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
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "docs/reference/admin-api.md"
    }
  ]
}
---



# Upload webdav

Upload the canonical connection representation through the configured upload direction.

The remote document and direction result are updated while protected other formats are not overwritten; service export includes configured secrets.
