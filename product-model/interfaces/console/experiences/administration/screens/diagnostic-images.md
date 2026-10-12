---
{
  "entities": [
    {
      "entity": "image-run",
      "shows": [
        "Prompt",
        "Model",
        "Mode",
        "Parameters",
        "Images",
        "Response metadata",
        "Time"
      ],
      "collects": [
        "Prompt",
        "Model",
        "Mode",
        "Parameters"
      ]
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



# Diagnostic images

The diagnostic image process presents successful local runs and the current generation or edit outcome.
