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
  "takesEffect": "Evaluated on each deployment sign-in request to the Management API entry.",
  "stability": "The setting governs that request. Changing it does not itself revoke established credentials; their validity rules remain separate.",
  "alternatives": [
    {
      "id": "sign-in-l-deployment-password",
      "selectedWhen": "Second factor enabled is false. A deployment without a second factor uses this form."
    },
    {
      "id": "sign-in-l-deployment-second-factor",
      "selectedWhen": "Second factor enabled is true."
    }
  ],
  "references": [
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

# Management API deployment second factor

Deployment sign-in through the Management API takes either the password alone or the password with the current second-factor code, as the deployment has chosen. Raw administrative Bearer authority is a separate contract.
