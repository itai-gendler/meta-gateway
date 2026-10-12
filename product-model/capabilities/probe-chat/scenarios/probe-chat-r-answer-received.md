---
{
  "kind": "primary",
  "routes": {
    "main": "R answer received"
  },
  "steps": [
    {
      "text": "Supply diagnostic local text history input and any selected forwarding destination pin.",
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
          "place": "console::administration::diagnostic-conversation"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The diagnostic answer is returned; no downstream booking is implied, and upstream consumption can still be charged.",
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








# Probe chat answer received

## Trigger

Supply diagnostic conversation input and any selected connection pin.

## Outcome

The diagnostic answer is returned; no downstream booking is implied, and upstream consumption can still be charged.
