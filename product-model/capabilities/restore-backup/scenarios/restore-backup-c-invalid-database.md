---
{
  "kind": "edge",
  "routes": {
    "main": "C invalid database"
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
      "text": "The selected snapshot fails database integrity/schema validation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "backup-restore"
        }
      }
    },
    {
      "text": "Restore stops before replacing the active database.",
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








# Restore backup invalid database

## Trigger

The selected snapshot fails database integrity/schema validation.

## Outcome

Restore stops before replacing the active database.
