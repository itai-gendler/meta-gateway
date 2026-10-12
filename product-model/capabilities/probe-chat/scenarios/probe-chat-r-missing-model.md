---
{
  "kind": "validation",
  "routes": {
    "main": "R missing model"
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
      "text": "The workbench input has no selected model.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-conversation"
        }
      }
    },
    {
      "text": "The local input is refused and no inference request is started.",
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








# Probe chat missing model

## Trigger

The workbench input has no selected model.

## Outcome

The local input is refused and no inference request is started.
