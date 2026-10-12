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



# Team settings

The Product-wide operating mode, branding and member visibility configuration.

## Information kept

- **Operating mode** — Personal or Team mode, affecting session and team-key admission.
- **Name** — the Product-facing name identifying this instance.
- **Logo** — the configured team logo content/address.
- **Notice** — the configured notice content.
- **Sign-in description** — the configured sign-in explanation.
- **API address** — the downstream API address presented to members.
- **Usage visibility** — whether the inspected member request and selected statistics surfaces are shown.
- **Routing visibility** — whether member personal-routing management is shown and admitted.
