---
{
  "kind": "primary",
  "routes": {
    "main": "A answer received"
  },
  "steps": [
    {
      "text": "Supply a message, model, parameters and owned Token selection.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::conversation"
        }
      },
      "actor": "member"
    },
    {
      "text": "Consult the Account token.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account-token",
          "effect": "reads",
          "facts": [
            "Credential"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::conversation"
        }
      },
      "actor": "member"
    },
    {
      "text": "Save changes to the Conversation.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "changes",
          "facts": [
            "Turns",
            "Model",
            "Parameters"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::personal::conversation"
        }
      },
      "actor": "member"
    },
    {
      "text": "The user turn and returned answer are retained locally; regular admission, health and recognized-usage booking apply.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::conversation"
        }
      },
      "actor": "member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/Playground.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/ImageStudio.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/runner.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/workbenchState.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/try.go"
    }
  ]
}
---








# Send message answer received

## Trigger

Supply a message, model, parameters and owned Token selection.

## Outcome

The user turn and returned answer are retained locally; regular admission, health and recognized-usage booking apply.
