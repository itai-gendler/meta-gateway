---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "route-member",
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
          "place": "inference-api"
        }
      ],
      "facts": [
        "Route",
        "Connection",
        "Group name",
        "Status",
        "Priority",
        "Weight",
        "Forwarded-name mapping",
        "Price layer",
        "Health",
        "Cooldown",
        "Manual intent",
        "Automatic origin"
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
      "configuredBy": "system-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "configuredBy": "account-token",
      "actors": [
        "gateway-client"
      ]
    },
    {
      "configuredBy": "access-policy",
      "actors": [
        "member"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Models.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_routes.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/route.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/routing.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/scoring.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/unify.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/model_alias.go"
    }
  ]
}
---



# Deployment administrator, Owner or Gateway client using System token or Gateway client using Account token or Member using Access policy may read Route member

Deployment administrator and Owner manage Route members. Personal access uses the current Policy-granted members. Inference follows the actual presented Token, fresh linked Account/Policy, selected/default owned plan and current member eligibility. Configured discovery and mapped health continuations modify only their corresponding bindings; Auto adoption requires the enabled configured connection and Auto mode.
