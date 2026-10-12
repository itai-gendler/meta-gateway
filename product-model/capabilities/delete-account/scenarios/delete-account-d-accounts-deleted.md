---
{
  "kind": "primary",
  "routes": {
    "main": "D accounts deleted"
  },
  "steps": [
    {
      "text": "Supply the selected local profile identities for deletion.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the Account token in Neutralized state. Remove the Account session. Remove the Routing plan. Remove the Third party identity. Remove the Recovery link. Remove the Member. Remove the Account.",
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
          "effect": "removes",
          "with": "account"
        },
        {
          "entity": "routing-plan",
          "effect": "removes",
          "with": "account"
        },
        {
          "entity": "third-party-identity",
          "effect": "removes",
          "with": "account"
        },
        {
          "entity": "recovery-link",
          "effect": "removes"
        },
        {
          "entity": "member",
          "effect": "removes"
        },
        {
          "entity": "account",
          "effect": "removes",
          "from": "Active",
          "with": "member"
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Non-full-administration role holder local profiles and selected dependent access are removed; full-administration role holder-row protection does not shield all dependent cleanup.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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








# Delete account accounts deleted

## Trigger

Supply the selected Account identities for deletion.

## Outcome

Non-owner Accounts and selected dependent access are removed; owner-row protection does not shield all dependent cleanup.
