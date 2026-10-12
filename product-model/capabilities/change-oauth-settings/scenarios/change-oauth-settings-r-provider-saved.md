---
{
  "kind": "primary",
  "routes": {
    "main": "R provider saved"
  },
  "steps": [
    {
      "text": "Supply provider client identity, endpoints, secret replacement and registration settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::oauth-settings"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the OAuth settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "oauth-settings",
          "effect": "changes",
          "facts": [
            "Providers",
            "Enabled providers",
            "Client identity",
            "Client secret availability",
            "Endpoints",
            "Registration",
            "Default policy"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::oauth-settings"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The provider settings are saved; blank secret preserves existing authority and blank client identity removes that provider.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::oauth-settings"
        }
      },
      "actor": "owner"
    }
  ],
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








# Change oauth settings provider saved

## Trigger

Supply provider client identity, endpoints, secret replacement and registration settings.

## Outcome

The provider settings are saved; blank secret preserves existing authority and blank client identity removes that provider.
