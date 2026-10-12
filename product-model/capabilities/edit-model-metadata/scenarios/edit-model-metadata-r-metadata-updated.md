---
{
  "kind": "primary",
  "routes": {
    "main": "R metadata updated"
  },
  "steps": [
    {
      "text": "Supply vendor, description, context/modalities/reasoning and whole-layer pricing facts.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the Model metadata.",
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
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::models"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The existing metadata definition is replaced by the saved supported model facts and pricing.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::models"
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








# Edit model metadata metadata updated

## Trigger

Supply vendor, description, context/modalities/reasoning and whole-layer pricing facts.

## Outcome

The existing metadata definition is replaced by the saved supported model facts and pricing.
