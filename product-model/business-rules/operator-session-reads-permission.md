---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "operator-session",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::entry"
        },
        {
          "place": "management-api::entry"
        },
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ],
      "facts": [
        "Credential",
        "Expires at"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator"
      ]
    },
    {
      "actors": [
        "owner"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/session.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/session.go#login"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_oauth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team.go"
    }
  ]
}
---



# Deployment administrator or Owner may read Operator session Credential, Expires at

Deployment administrator and Owner establish or use operator authority through their implemented authentication branch. Browser sign-out forgets the locally held signed credential; it does not revoke every copy of that authority.
