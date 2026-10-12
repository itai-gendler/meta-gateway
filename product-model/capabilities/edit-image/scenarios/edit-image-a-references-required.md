---
{
  "kind": "validation",
  "routes": {
    "main": "A references required"
  },
  "steps": [
    {
      "text": "Supply prompt, model, parameters and required reference images.",
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
      "text": "Image edit has no required reference image.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::images"
        }
      }
    },
    {
      "text": "The edit input is refused before an upstream image write.",
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








# Edit image references required

## Trigger

Image edit has no required reference image.

## Outcome

The edit input is refused before an upstream image write.
