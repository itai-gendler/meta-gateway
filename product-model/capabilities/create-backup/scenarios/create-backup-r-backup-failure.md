---
{
  "kind": "edge",
  "routes": {
    "main": "R backup failure"
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
      "text": "Snapshot creation or verification fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::backups"
        }
      }
    },
    {
      "text": "Failure information is returned/retained and no partially verified file is published as a valid snapshot.",
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








# Create backup backup failure

## Trigger

Snapshot creation or verification fails.

## Outcome

Failure information is returned/retained and no partially verified file is published as a valid snapshot.
