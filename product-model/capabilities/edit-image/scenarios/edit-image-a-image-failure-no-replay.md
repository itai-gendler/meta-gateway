---
{
  "kind": "edge",
  "routes": {
    "main": "A image failure no replay"
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
      "text": "The upstream image write fails or returns no usable image output.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::personal::images"
        }
      }
    },
    {
      "text": "The failure/current outcome is returned without replay; no successful browser saved image result is saved.",
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








# Edit image image failure no replay

## Trigger

The upstream image write fails or returns no usable image output.

## Outcome

The failure/current outcome is returned without replay; no successful browser Image run is saved.
