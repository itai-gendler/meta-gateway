---
{
  "kind": "validation",
  "routes": {
    "main": "R missing target"
  },
  "steps": [
    {
      "text": "Select the answer to regenerate.",
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
      "text": "The selected assistant answer no longer exists in the local history.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-conversation"
        }
      }
    },
    {
      "text": "Regeneration does not run for a missing target.",
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








# Regenerate answer missing target

## Trigger

The selected assistant answer no longer exists in the local history.

## Outcome

Regeneration does not run for a missing target.
