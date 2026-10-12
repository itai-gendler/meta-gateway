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
  ],
  "singleton": true
}
---



# OAuth settings

The Product-wide external sign-in provider and registration configuration.

## Information kept

- **Providers** — the configured GitHub and Linux.do provider entries.
- **Enabled providers** — the configured providers available for sign-in.
- **Client identity** — the OAuth client identifier; clearing it removes that provider configuration.
- **Client secret availability** — whether a stored OAuth client secret exists without disclosing it.
- **Endpoints** — the provider's browser authorization endpoint and gateway token/user-information endpoints.
- **Registration** — whether an unbound external subject may establish an Account.
- **Default policy** — the policy assigned by configured OAuth registration.
