---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/ModePanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/OAuthPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_oauth_admin.go"
    }
  ]
}
---




# Third party identity

A provider subject associated with an Account for configured external sign-in.

## Information kept

- **Provider** — the configured external identity-provider kind.
- **Subject** — the stable external user identifier returned by the selected identity provider.
- **Account** — the associated Account, without implying current credential eligibility.
- **Profile name** — the observed external profile name.
- **Email** — the observed external email information.
- **Last sign-in** — the last successful sign-in using this external identity.
