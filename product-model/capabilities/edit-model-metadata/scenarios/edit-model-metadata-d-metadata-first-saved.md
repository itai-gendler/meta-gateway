---
{
  "kind": "primary",
  "routes": {
    "main": "D metadata first saved"
  },
  "steps": [
    {
      "text": "Supply vendor, description, context/modalities/reasoning and whole-layer pricing facts.",
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
      "text": "Establish the Model metadata.",
      "kind": "product",
      "entities": [
        {
          "entity": "model-metadata",
          "effect": "creates",
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
      "text": "The first metadata definition is retained for the model through Save, with configured pricing and ownership.",
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








# Edit model metadata metadata first saved

## Trigger

Supply vendor, description, context/modalities/reasoning and whole-layer pricing facts.

## Outcome

The first metadata definition is retained for the model through Save, with configured pricing and ownership.
