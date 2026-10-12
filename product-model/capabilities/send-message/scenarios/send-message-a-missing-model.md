---
{
  "kind": "validation",
  "routes": {
    "main": "A missing model"
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
      "text": "The workbench input has no selected model.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::conversation"
        }
      }
    },
    {
      "text": "The local input is refused and no inference request is started.",
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








# Send message missing model

## Trigger

The workbench input has no selected model.

## Outcome

The local input is refused and no inference request is started.
