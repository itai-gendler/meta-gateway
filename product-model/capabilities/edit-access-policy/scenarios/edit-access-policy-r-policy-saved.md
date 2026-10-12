---
{
  "kind": "primary",
  "routes": {
    "main": "R policy saved"
  },
  "steps": [
    {
      "text": "Supply replacement policy settings.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the Access policy.",
      "kind": "product",
      "entities": [
        {
          "entity": "access-policy",
          "effect": "changes",
          "facts": [
            "Name",
            "All models",
            "Models",
            "Route members",
            "Token limit",
            "Request rate",
            "Personal routing",
            "Request preference editing"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The policy is updated; subsequent linked-local profile checks use the current definition.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::access-and-routing"
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








# Edit access policy policy saved

## Trigger

Supply replacement policy settings.

## Outcome

The policy is updated; subsequent linked-account checks use the current definition.
