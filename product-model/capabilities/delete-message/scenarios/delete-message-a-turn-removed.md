---
{
  "kind": "primary",
  "routes": {
    "main": "A turn removed"
  },
  "steps": [
    {
      "text": "Select the turn to delete.",
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
      "text": "Save changes to the Conversation.",
      "kind": "product",
      "entities": [
        {
          "entity": "conversation",
          "effect": "changes",
          "facts": [
            "Turns"
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
      "text": "The selected turn is removed; deleting a user turn also removes its immediately following assistant reply.",
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








# Delete message turn removed

## Trigger

Select the turn to delete.

## Outcome

The selected turn is removed; deleting a user turn also removes its immediately following assistant reply.
