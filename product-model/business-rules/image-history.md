---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "generate-image"
    },
    {
      "type": "capability",
      "id": "edit-image"
    },
    {
      "type": "capability",
      "id": "probe-image-generation"
    },
    {
      "type": "capability",
      "id": "probe-image-edit"
    },
    {
      "type": "capability",
      "id": "delete-image-run"
    },
    {
      "type": "capability",
      "id": "clear-image-runs"
    },
    {
      "type": "entity",
      "id": "image-run"
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



# Only successful producing browser image results enter bounded local history

Only image-producing successful browser calls save a run. Current errors or missing image outputs are not saved successful states. The recent history is approximately twelve runs/48 MB, with oldest trimming and storage-pressure recovery; persistence remains best effort. Run reuse restores input/result and does not generate another image.
