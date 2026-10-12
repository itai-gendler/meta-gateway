---
{
  "kind": "configuration",
  "of": "capability-scenario",
  "settings": [
    {
      "entity": "operator-settings",
      "fact": "Second factor enabled"
    }
  ],
  "takesEffect": "Selection is evaluated for the deployment sign-in attempt on the chosen Console or Management API entry contract.",
  "stability": "The setting governs that attempt. Changing it does not itself revoke established credentials; their validity rules remain separate.",
  "alternatives": [
    {
      "id": "sign-in-p-deployment-password",
      "selectedWhen": "Console entry is used and deployment second factor is disabled."
    },
    {
      "id": "sign-in-p-deployment-second-factor",
      "selectedWhen": "Console entry is used and deployment second factor is enabled."
    },
    {
      "id": "sign-in-l-deployment-password",
      "selectedWhen": "Management API entry is used and deployment second factor is disabled."
    },
    {
      "id": "sign-in-l-deployment-second-factor",
      "selectedWhen": "Management API entry is used and deployment second factor is enabled."
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



# Deployment second factor

Deployment sign-in supports password-only or password plus the configured second-factor response, selected before establishing its operator credential. Account-password sign-in and raw administrative Bearer authority remain separate contracts.
