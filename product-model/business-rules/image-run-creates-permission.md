---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "image-run",
      "effect": "creates",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "console::personal"
        }
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "actors": [
        "member"
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



# Deployment administrator, Owner or Member may create Image run

Deployment administrator and Owner use diagnostic image history; Member uses personal image history in the current browser context. Only successful image-producing results are saved; reuse restores the form/result without inference.
