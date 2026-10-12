---
{
  "kind": "primary",
  "routes": {
    "main": "C database restored"
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
      "text": "Consult the Backup.",
      "kind": "condition",
      "entities": [
        {
          "entity": "backup",
          "effect": "reads",
          "facts": [
            "Name",
            "File availability",
            "Checksum",
            "Snapshot contents"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "backup-restore"
        }
      },
      "actor": "backup-operator"
    },
    {
      "text": "Save changes to the Account. Remove the Account session. Save changes to the Invitation code. Save changes to the Credit code. Save changes to the Recovery link.",
      "kind": "product",
      "entities": [
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Login name",
            "Display name",
            "Status",
            "Password credential",
            "Policy",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request preferences",
            "Token count",
            "Session revision"
          ]
        },
        {
          "entity": "account-session",
          "effect": "removes"
        },
        {
          "entity": "invitation-code",
          "effect": "changes",
          "facts": [
            "Revocation"
          ]
        },
        {
          "entity": "credit-code",
          "effect": "changes",
          "facts": [
            "Revocation"
          ]
        },
        {
          "entity": "recovery-link",
          "effect": "changes",
          "facts": [
            "Revocation"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "backup-restore"
        }
      },
      "actor": "backup-operator"
    },
    {
      "text": "The database contents are restored; local profile sessions are cleared and all team-code purposes revoked, without blanket downstream-Token revocation.",
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








# Restore backup database restored

## Trigger

Select a named accessible backup for offline restoration.

## Outcome

The database contents are restored; Account sessions are cleared and all team-code purposes revoked, without blanket downstream-Token revocation.
