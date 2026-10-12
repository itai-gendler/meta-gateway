---
{
  "kind": "primary",
  "routes": {
    "main": "A edited image result"
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
      "text": "Consult the Account token.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account-token",
          "effect": "reads",
          "facts": [
            "Credential"
          ]
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
          "place": "console::personal::images"
        }
      },
      "actor": "member"
    },
    {
      "text": "Image-producing success returns the outputs; browser use retains a successful run, while direct API use returns the response without browser history.",
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








# Edit image edited image result

## Trigger

Supply prompt, model, parameters and required reference images.

## Outcome

Image-producing success retains an Image run with its prompt, model, parameters and outputs in browser history.

## Edge cases

- A response with no image output is a current outcome and is not saved as a successful browser run.
- Reusing a saved run restores form/result information without initiating inference.
