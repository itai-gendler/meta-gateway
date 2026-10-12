---
{
  "kind": "primary",
  "routes": {
    "main": "R models listed"
  },
  "steps": [
    {
      "text": "Read the available model catalog.",
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
      "text": "Consult the Route. Consult the Model metadata. Consult the Model capability.",
      "kind": "condition",
      "entities": [
        {
          "entity": "route",
          "effect": "reads",
          "facts": [
            "Model name/pattern",
            "Status"
          ]
        },
        {
          "entity": "model-metadata",
          "effect": "reads",
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
          "effect": "reads",
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
      },
      "actor": "owner"
    },
    {
      "text": "The permitted catalog projection is returned; a listed model need not have a presently usable upstream.",
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








# Browse models models listed

## Trigger

Read the available model catalog.

## Outcome

The permitted catalog projection is returned; a listed model need not have a presently usable upstream.
