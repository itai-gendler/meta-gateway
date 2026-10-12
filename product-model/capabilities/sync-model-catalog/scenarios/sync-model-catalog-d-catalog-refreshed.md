---
{
  "kind": "primary",
  "routes": {
    "main": "D catalog refreshed"
  },
  "steps": [
    {
      "text": "Request or schedule catalog refresh.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Current catalog-owned metadata and callable capability facts are refreshed; failures remain observable without changing the originating save result.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
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








# Sync model catalog catalog refreshed

## Trigger

Request or schedule catalog refresh.

## Outcome

Current catalog-owned metadata and callable capability facts are refreshed; failures remain observable without changing the originating save result.
