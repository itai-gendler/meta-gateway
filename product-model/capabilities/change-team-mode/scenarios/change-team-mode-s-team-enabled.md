---
{
  "kind": "primary",
  "routes": {
    "main": "S team enabled"
  },
  "steps": [
    {
      "text": "Choose the operating mode.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "deployment-administrator"
    },
    {
      "text": "Save changes to the Team settings.",
      "kind": "product",
      "entities": [
        {
          "entity": "team-settings",
          "effect": "changes",
          "facts": [
            "Operating mode"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "deployment-administrator"
    },
    {
      "text": "When no full-administration association exists, establish the first held-role association and its new local profile.",
      "kind": "product",
      "actor": "deployment-administrator",
      "entities": [
        {
          "entity": "owner",
          "effect": "creates",
          "facts": [
            "Account association"
          ]
        },
        {
          "entity": "account",
          "effect": "creates",
          "to": "Active",
          "facts": [
            "Login name",
            "Display name",
            "Status",
            "Password credential",
            "Policy",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request preferences",
            "Token count",
            "Session revision"
          ],
          "with": "owner"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Team mode is saved. Existing full-administration role holder association is retained; if absent, first-full-administration role holder establishment uses deployment authority.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::setup"
        }
      },
      "actor": "deployment-administrator"
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









# Change team mode team enabled

## Trigger

Choose the operating mode.

## Outcome

Team mode is saved. Existing Owner association is retained; if absent, first-owner establishment uses deployment authority.


## Decision points

### Existing Owner association

Does the Product already retain an Owner association? Both branches finish in Team mode; an existing Owner is not replaced.

- Existing association → retain it and save Team mode.
- No association → establish the first Owner using deployment authority, then save Team mode.
