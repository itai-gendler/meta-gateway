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
  "domain": "backups",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/ops/BackupsPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/backup.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/backup/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "cmd/server/main.go"
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "docs/reference/admin-api.md"
    }
  ]
}
---



# Create backup

Publish a validated online database snapshot and apply configured retention.

A verified named snapshot is published with integrity metadata; failed creation is distinguished and does not publish a partial snapshot.
