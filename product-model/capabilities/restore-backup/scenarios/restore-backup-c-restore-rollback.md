---
{
  "kind": "edge",
  "routes": {
    "main": "C restore rollback"
  },
  "steps": [
    {
      "text": "Select a named accessible snapshot for offline restoration.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "backup-restore"
        }
      },
      "actor": "backup-operator"
    },
    {
      "text": "Snapshot replacement fails after the current database was moved aside.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "backup-restore"
        }
      }
    },
    {
      "text": "The previous database and applicable sidecar state are restored; the source snapshot is retained.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "backup-restore"
        }
      },
      "actor": "backup-operator"
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








# Restore backup restore rollback

## Trigger

Snapshot replacement fails after the current database was moved aside.

## Outcome

The previous database and applicable sidecar state are restored; the source snapshot is retained.
