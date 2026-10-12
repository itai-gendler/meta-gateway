---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "edit-account-profile"
    },
    {
      "type": "capability",
      "id": "change-account-role"
    },
    {
      "type": "capability",
      "id": "pause-account"
    },
    {
      "type": "capability",
      "id": "resume-account"
    },
    {
      "type": "capability",
      "id": "adjust-account-quota"
    },
    {
      "type": "capability",
      "id": "reset-account-usage"
    },
    {
      "type": "capability",
      "id": "revoke-account-sessions"
    },
    {
      "type": "entity",
      "id": "account-session"
    },
    {
      "type": "entity",
      "id": "account"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ]
}
---



# Individual security changes and bulk operations retain their distinct session effects

Individual Account updates increment revision and delete sessions; bulk pause/resume does likewise; bulk policy assignment does not; explicit bulk session revocation deletes without revision increment
