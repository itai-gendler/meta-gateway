---
{
  "kind": "primary",
  "routes": {
    "main": "D invitation issued"
  },
  "steps": [
    {
      "text": "Supply code kind, assignment/grant, label, validity, use limit and batch count.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "Establish the Invitation code.",
      "kind": "product",
      "entities": [
        {
          "entity": "invitation-code",
          "effect": "creates",
          "facts": [
            "Code credential",
            "Label",
            "Assigned role",
            "Policy",
            "Initial tokens",
            "Initial money",
            "Validity",
            "Use limit",
            "Uses",
            "Revocation"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "administrator"
    },
    {
      "text": "invitation authoritys retain their assigned role, policy, initial budgets and usage validity, with plaintext returned once.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "administrator"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/CodePanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go"
    }
  ]
}
---








# Create code invitation issued

## Trigger

Supply code kind, assignment/grant, label, validity, use limit and batch count.

## Outcome

Invitation codes retain their assigned role, policy, initial budgets and usage validity, with plaintext returned once.
