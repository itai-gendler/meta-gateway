---
{
  "kind": "validation",
  "routes": {
    "main": "R empty message"
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
      "text": "The resubmitted replacement turn contains no usable message content.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-conversation"
        }
      }
    },
    {
      "text": "Resubmission is refused and no replacement inference request is started.",
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








# Resubmit message empty message

## Trigger

The resubmitted replacement turn contains no usable message content.

## Outcome

Resubmission is refused and no replacement inference request is started.
