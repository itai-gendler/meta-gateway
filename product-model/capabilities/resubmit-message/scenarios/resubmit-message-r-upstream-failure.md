---
{
  "kind": "edge",
  "routes": {
    "main": "R upstream failure"
  },
  "steps": [
    {
      "text": "Supply non-empty replacement content and Save and submit.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-conversation"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The admitted call fails at its configured upstream.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-conversation"
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
          "place": "console::administration::diagnostic-conversation"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The edited selected turn and truncated following history remain. The new assistant turn retains received partial content with the observed upstream error and is excluded from later transmitted history.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-conversation"
        }
      },
      "actor": "owner"
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









# Resubmit message upstream failure

## Trigger

The admitted call fails at its configured upstream.

## Outcome

The edited selected turn and truncated following history remain. The new assistant turn retains received partial content with the observed upstream error and is excluded from later transmitted history.
