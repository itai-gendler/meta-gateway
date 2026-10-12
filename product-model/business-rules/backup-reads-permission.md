---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "backup",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "backup-restore"
        }
      ],
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
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "actors": [
        "backup-operator"
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



# Deployment administrator, Owner or Backup operator may read Backup

Deployment administrator and Owner create or list online snapshots. Backup operator reads the selected offline snapshot in the host environment. Online application authentication is not an additional offline restoration gate.
