---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "webdav-settings",
      "effect": "changes",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ],
      "facts": [
        "Last result"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "unattended": true
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



# Deployment administrator, Owner or the scheduled Product may change WebDAV settings Last result

Deployment administrator and Owner configure directions and run manual WebDAV operations. Scheduled execution reads its actual configuration and records success, failure or skipped Last result, including a disabled direction's skipped outcome. Scheduled result updates grant no credential or schedule editing.
