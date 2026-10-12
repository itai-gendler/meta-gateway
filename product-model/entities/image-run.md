---
{
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
  ],
  "domain": "workbench"
}
---




# Image run

A successful image-producing browser result retained for viewing and form reuse.

## Information kept

- **Prompt** — the prompt supplied for the successful image run.
- **Model** — the model used for this successful image-producing run.
- **Mode** — Generation or Edit, including reference-driven automatic planning.
- **Parameters** — the model and generation/edit request parameters retained with this successful image-producing browser result.
- **Images** — the returned image outputs retained for reuse and viewing.
- **Response metadata** — the retained successful image result metadata.
- **Time** — the time this successful image result was recorded.
