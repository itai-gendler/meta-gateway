---
{
  "type": "cli",
  "actors": [
    "backup-operator"
  ],
  "languages": [
    "en"
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
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "docs/operations/backup-restore.md"
    }
  ]
}
---



# Backup restore

The offline contract for validating and restoring a named database snapshot.
