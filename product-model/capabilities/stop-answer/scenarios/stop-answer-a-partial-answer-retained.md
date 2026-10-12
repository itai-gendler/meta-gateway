---
{
  "kind": "primary",
  "routes": {
    "main": "A partial answer retained"
  },
  "steps": [
    {
      "text": "Stop the active answer.",
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
      "text": "Partial answer/reasoning and a stopped marker remain in local history.",
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








# Stop answer partial answer retained

## Trigger

Stop the active answer.

## Outcome

Partial answer/reasoning and a stopped marker remain in local history.
