---
{
  "kind": "validation",
  "routes": {
    "main": "R owner required"
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
      "actor": "administrator"
    },
    {
      "text": "The operation is submitted by a limited staff principal rather than a full administrative principal.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::oauth-settings"
        }
      }
    },
    {
      "text": "The operation returns full-administration role holder-required without its requested mutation.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::oauth-settings"
        }
      },
      "actor": "administrator"
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








# Change oauth settings owner required

## Trigger

The operation is submitted by an Administrator rather than a full administrative principal.

## Outcome

The operation returns owner-required without its requested mutation.
