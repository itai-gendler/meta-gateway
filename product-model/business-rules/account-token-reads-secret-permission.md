---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "account-token",
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
        }
      ],
      "facts": [
        "Credential"
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
      "related": [
        {
          "verb": "owns",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "member"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Keys.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_keys.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/downstream_key.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    }
  ]
}
---



# Deployment administrator, Owner or the related Member may read Account token Credential

A related Member creates an owned Token below the current Policy count limit and reads its retained metadata or explicitly revealable secret. Full administrators manage retained Account tokens through administration. Personal edits are limited to Name, Model restrictions, Expiry, IP restrictions, Routing plan and Status; ownership, scopes, groups, denylist and budgets/counters are closed to personal editing. Own rotation, toggling and neutralization retain their implemented boundaries; physical removal requires full administration. Inference uses the actual presented credential and fresh linked active Account, Team mode and current Policy checks. Legacy unused price columns convey no editable pricing meaning.
