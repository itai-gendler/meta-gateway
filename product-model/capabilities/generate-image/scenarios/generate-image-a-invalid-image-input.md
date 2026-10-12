---
{
  "kind": "validation",
  "routes": {
    "main": "A invalid image input"
  },
  "steps": [
    {
      "text": "Supply prompt, model and image parameters.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::images"
        }
      },
      "actor": "member"
    },
    {
      "text": "The generation/edit input fails its supported prompt, format or image limits.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::images"
        }
      }
    },
    {
      "text": "The image request is rejected before executing the invalid input.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::images"
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








# Generate image invalid image input

## Trigger

The generation/edit input fails its supported prompt, format or image limits.

## Outcome

The image request is rejected before executing the invalid input.
