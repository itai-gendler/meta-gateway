---
{
  "availability": [
    {
      "place": "backup-restore"
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



# Restore backup

Validate and replace the offline database from a selected named snapshot, with rollback on replacement failure.

The database contents are restored; Account sessions are cleared and all team-code purposes revoked, without blanket downstream-Token revocation.
