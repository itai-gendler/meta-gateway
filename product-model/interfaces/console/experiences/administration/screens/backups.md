---
{
  "entities": [
    {
      "entity": "backup",
      "shows": [
        "Name",
        "Time",
        "Size",
        "Checksum",
        "Outcome",
        "Failure information",
        "File availability"
      ]
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



# Backups

The published snapshot inventory shows integrity, file availability and creation outcomes.
