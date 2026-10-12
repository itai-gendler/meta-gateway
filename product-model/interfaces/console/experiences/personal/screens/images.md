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
    },
    {
      "entity": "account-token",
      "shows": [
        "Name",
        "Credential hint"
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



# Images

The personal image process presents successful local runs and the current regular gateway outcome.
