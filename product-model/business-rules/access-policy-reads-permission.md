---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "access-policy",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::personal"
        },
        {
          "place": "console::entry"
        },
        {
          "place": "management-api::entry"
        },
        {
          "place": "inference-api"
        }
      ],
      "facts": [
        "Name",
        "All models",
        "Models",
        "Route members",
        "Token limit",
        "Request rate",
        "Personal routing",
        "Request preference editing"
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
        "administrator"
      ]
    },
    {
      "configuredBy": "account"
    },
    {
      "configuredBy": "invitation-code"
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "gateway-client"
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



# Deployment administrator, Owner or Administrator or execution under Account or execution under Invitation code or Gateway client using Account token may read Access policy

Deployment administrator and Owner configure Policies. Administrator can read assignment choices within its team-management scope. Account access, invitation assignment and inference consult the actual applicable Policy; its current model/member grants constrain those uses. Default and referenced Policies retain their deletion protection.
