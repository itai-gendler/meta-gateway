---
{
  "kind": "primary",
  "routes": {
    "main": "A history cleared"
  },
  "steps": [
    {
      "text": "Clear local image history.",
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
          "place": "console::personal::images"
        }
      },
      "actor": "member"
    },
    {
      "text": "The retained browser image-run history is empty.",
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








# Clear image runs history cleared

## Trigger

Clear local image history.

## Outcome

The retained browser image-run history is empty.
