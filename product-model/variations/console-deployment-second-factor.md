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
  "takesEffect": "Evaluated on each deployment sign-in attempt at the Console entry.",
  "stability": "The setting governs that attempt. Changing it does not itself revoke established credentials; their validity rules remain separate.",
  "alternatives": [
    {
      "id": "sign-in-p-deployment-password",
      "selectedWhen": "Second factor enabled is false. A deployment without a second factor uses this form."
    },
    {
      "id": "sign-in-p-deployment-second-factor",
      "selectedWhen": "Second factor enabled is true."
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
      "target": "internal/httpapi/session.go#login"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/totp/totp.go"
    }
  ]
}
---

# Console deployment second factor

Deployment sign-in on the Console is either password only or password plus the current second-factor code, and the deployment chooses which before anyone signs in. Account-password sign-in is a separate contract.
