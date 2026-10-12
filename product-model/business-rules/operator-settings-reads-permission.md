---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "operator-settings",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::entry"
        },
        {
          "place": "management-api::entry"
        }
      ],
      "facts": [
        "Login name",
        "Deployment credential",
        "Token-login availability",
        "Owner claim",
        "Second factor enabled",
        "Secret export allowance"
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
      "configuredBy": "operator-settings"
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



# Deployment administrator, Owner or execution under Operator settings may read Operator settings

Entry processes consult operator login identity and entry availability. Full administrators and the actual operator configuration support the relevant administrative checks. Entry-facing reads do not disclose the deployment password or secret material.
