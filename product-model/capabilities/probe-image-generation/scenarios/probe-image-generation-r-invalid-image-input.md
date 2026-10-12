---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid image input"
  },
  "steps": [
    {
      "text": "Supply prompt, model and image parameters.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-images"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The generation/edit input fails its supported prompt, format or image limits.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-images"
        }
      }
    },
    {
      "text": "The image request is rejected before executing the invalid input.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-images"
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








# Probe image generation invalid image input

## Trigger

The generation/edit input fails its supported prompt, format or image limits.

## Outcome

The image request is rejected before executing the invalid input.
