---
{
  "kind": "edge",
  "routes": {
    "main": "R owner id dependents affected"
  },
  "steps": [
    {
      "text": "Supply the selected local profile identities for deletion.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The submitted deletion set includes the protected full-administration role holder ID along with allowed deletion processing.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      }
    },
    {
      "text": "Save changes to the Account token in Neutralized state. Remove the Account session. Remove the Routing plan. Remove the Third party identity. Remove the Recovery link.",
      "kind": "product",
      "entities": [
        {
          "entity": "account-token",
          "effect": "changes",
          "facts": [
            "Status",
            "Credential",
            "Neutralization",
            "Account"
          ],
          "to": "Neutralized",
          "from": "Enabled"
        },
        {
          "entity": "account-session",
          "effect": "removes"
        },
        {
          "entity": "routing-plan",
          "effect": "removes"
        },
        {
          "entity": "third-party-identity",
          "effect": "removes"
        },
        {
          "entity": "recovery-link",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Remove the selected subjects from retained Credit code redemption history without changing face values or consumed use counts.",
      "kind": "product",
      "entities": [
        {
          "entity": "credit-code",
          "effect": "changes",
          "facts": [
            "Redemptions"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The full-administration role holder row remains, but unfiltered IDs reach dependent cleanup, so associated sessions/plans/identities/recovery authority and Token stored authority may be affected.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ]
}
---








# Delete account owner id dependents affected

## Trigger

The submitted deletion set includes the protected Owner ID along with allowed deletion processing.

## Outcome

The Owner row remains, but unfiltered IDs reach dependent cleanup, so associated sessions/plans/identities/recovery authority and Token stored authority may be affected.
