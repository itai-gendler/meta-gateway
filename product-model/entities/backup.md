---
{
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
  ],
  "domain": "backups"
}
---




# Backup

A named published snapshot with integrity information and recoverable database contents.

## Information kept

- **Name** — the Product-facing name identifying this instance.
- **Time** — the creation time of the named database snapshot.
- **Size** — the published backup size.
- **Checksum** — the backup integrity digest.
- **Outcome** — the most recent snapshot creation or integrity-check outcome.
- **Failure information** — the observed backup creation/validation failure detail.
- **File availability** — whether the named published snapshot is present.
- **Snapshot contents** — the retained database snapshot used to replace current database information.
