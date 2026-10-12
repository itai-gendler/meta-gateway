---
{
  "kind": "validation",
  "routes": {
    "main": "R references required"
  },
  "steps": [
    {
      "text": "Supply prompt, model, parameters and required reference images.",
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
      "text": "Image edit has no required reference image.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::diagnostic-images"
        }
      }
    },
    {
      "text": "The edit input is refused before an upstream image write.",
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








# Probe image edit references required

## Trigger

Image edit has no required reference image.

## Outcome

The edit input is refused before an upstream image write.
