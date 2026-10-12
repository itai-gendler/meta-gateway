---
{
  "kind": "primary",
  "routes": {
    "main": "R backup created"
  },
  "steps": [
    {
      "text": "Request a database snapshot.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::backups"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Establish the Backup.",
      "kind": "product",
      "entities": [
        {
          "entity": "backup",
          "effect": "creates",
          "facts": [
            "Name",
            "Time",
            "Size",
            "Checksum",
            "Outcome",
            "Failure information",
            "File availability",
            "Snapshot contents"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::backups"
        }
      },
      "actor": "owner"
    },
    {
      "text": "A verified named snapshot is published with integrity metadata; failed creation is distinguished and does not publish a partial snapshot.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::backups"
        }
      },
      "actor": "owner"
    }
  ],
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
    }
  ]
}
---








# Create backup backup created

## Trigger

Request a database backup.

## Outcome

A verified named snapshot is published with integrity metadata; failed creation is distinguished and does not publish a partial snapshot.
