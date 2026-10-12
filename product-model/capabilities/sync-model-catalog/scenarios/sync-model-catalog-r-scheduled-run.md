---
{
  "kind": "primary",
  "routes": {
    "main": "R scheduled run"
  },
  "steps": [
    {
      "text": "The configured schedule is due.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "unattended": true
    },
    {
      "text": "Save changes to the Model metadata. Save changes to the Model capability.",
      "kind": "product",
      "entities": [
        {
          "entity": "model-metadata",
          "effect": "changes",
          "facts": [
            "Model name",
            "Vendor",
            "Description",
            "Context limit",
            "Modalities",
            "Reasoning",
            "Price layer",
            "Classification source"
          ]
        },
        {
          "entity": "model-capability",
          "effect": "changes",
          "facts": [
            "Model name",
            "Endpoints",
            "Input modalities",
            "Output modalities",
            "Image formats",
            "Image limits",
            "Classification source"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      }
    },
    {
      "text": "Current catalog-owned metadata and callable capability facts are refreshed; failures remain observable without changing the originating save result.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Models.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_routes.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/route.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/routing.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/scoring.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/unify.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/model_alias.go"
    }
  ]
}
---








# Sync model catalog scheduled run

## Trigger

The configured schedule becomes due for refresh configured external model-catalog information without overwriting protected ownership.

## Outcome

Current catalog-owned metadata and callable capability facts are refreshed; failures remain observable without changing the originating save result.
