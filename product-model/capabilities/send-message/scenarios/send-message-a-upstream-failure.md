---
{
  "kind": "edge",
  "routes": {
    "main": "A upstream failure"
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
      "text": "The admitted call fails at its configured upstream.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::conversation"
        }
      }
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
      "text": "The submitted user turn remains and its assistant turn retains received partial content with the observed upstream error. Error turns are excluded from later transmitted transcript.",
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










# Send message upstream failure

## Trigger

The admitted call fails at its configured upstream.

## Outcome

The submitted user turn remains and its assistant turn retains received partial content with the observed upstream error. Error turns are excluded from later transmitted conversation history.
