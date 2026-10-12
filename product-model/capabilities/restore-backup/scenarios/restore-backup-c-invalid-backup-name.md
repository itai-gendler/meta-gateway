---
{
  "kind": "validation",
  "routes": {
    "main": "C invalid backup name"
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
      "text": "The requested snapshot name fails the supported safe-name validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "backup-restore"
        }
      }
    },
    {
      "text": "Restore is rejected before replacing the current database.",
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








# Restore backup invalid backup name

## Trigger

The requested snapshot name fails the supported safe-name validation.

## Outcome

Restore is rejected before replacing the current database.
