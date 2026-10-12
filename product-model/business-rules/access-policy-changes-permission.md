---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "access-policy",
      "effect": "changes",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
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



# Deployment administrator, Owner may change Access policy

Deployment administrator and Owner configure Policies. Administrator can read assignment choices within its team-management scope. Account access, invitation assignment and inference consult the actual applicable Policy; its current model/member grants constrain those uses. Default and referenced Policies retain their deletion protection.
