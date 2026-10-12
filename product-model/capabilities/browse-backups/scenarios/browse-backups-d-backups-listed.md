---
{
  "kind": "primary",
  "routes": {
    "main": "D backups listed"
  },
  "steps": [
    {
      "text": "Read the snapshot inventory.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Backup.",
      "kind": "condition",
      "entities": [
        {
          "entity": "backup",
          "effect": "reads",
          "facts": [
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
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Named snapshots show creation time, size, checksum and creation/validation information.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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








# Browse backups backups listed

## Trigger

Read the backup inventory.

## Outcome

Named snapshots show creation time, size, checksum and creation/validation information.
