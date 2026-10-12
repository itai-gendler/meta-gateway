---
{
  "kind": "primary",
  "routes": {
    "main": "R history cleared"
  },
  "steps": [
    {
      "text": "Clear local image history.",
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
      "text": "Remove the Image run.",
      "kind": "product",
      "entities": [
        {
          "entity": "image-run",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-images"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The retained browser image-run history is empty.",
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








# Clear image runs history cleared

## Trigger

Clear local image history.

## Outcome

The retained browser image-run history is empty.
