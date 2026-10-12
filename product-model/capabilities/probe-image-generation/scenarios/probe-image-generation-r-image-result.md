---
{
  "kind": "primary",
  "routes": {
    "main": "R image result"
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
      "text": "Establish the Image run.",
      "kind": "product",
      "entities": [
        {
          "entity": "image-run",
          "effect": "creates",
          "facts": [
            "Prompt",
            "Model",
            "Mode",
            "Parameters",
            "Images",
            "Response metadata",
            "Time"
          ]
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
      "text": "Image-producing success returns the outputs; browser use retains a successful run, while direct API use returns the response without browser history.",
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








# Probe image generation image result

## Trigger

Supply prompt, model and image parameters.

## Outcome

Image-producing success retains an Image run with its prompt, model, parameters and outputs in browser history.

## Edge cases

- A response with no image output is a current outcome and is not saved as a successful browser run.
- Reusing a saved run restores form/result information without initiating inference.
