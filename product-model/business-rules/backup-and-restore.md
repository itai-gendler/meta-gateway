---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-backup"
    },
    {
      "type": "capability",
      "id": "restore-backup"
    },
    {
      "type": "entity",
      "id": "backup"
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



# Restore validates and rolls back replacement while invalidating sessions and codes

Online creation publishes only a verified snapshot and applies configured count retention. Offline restore validates integrity/schema before replacing the current database and retains a rollback point for replacement failure, including applicable sidecars. Successful restore replaces retained database information with Snapshot contents, clears Account sessions and revokes invitation, credit and recovery purposes. It does not blanket-revoke downstream Tokens; old snapshot authority/settings can return. The source snapshot is retained, and database validity alone does not prove decryptability under changed deployment key material.
