---
{
  "entities": [
    {
      "entity": "webdav-settings",
      "shows": [
        "Download connection",
        "Upload connection",
        "Credential availability",
        "Direction enablement",
        "Schedules",
        "Last result"
      ],
      "collects": [
        "Download connection",
        "Upload connection",
        "Credential availability",
        "Direction enablement",
        "Schedules"
      ]
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



# WebDAV

The remote synchronization subject retains independent direction settings and the most recent execution result.
