---
{
  "entities": [
    {
      "entity": "route",
      "shows": [
        "Model name/pattern",
        "Status",
        "Routing mode",
        "Single member",
        "Forwarded-name mapping",
        "Routing overrides"
      ],
      "collects": [
        "Model name/pattern",
        "Status",
        "Routing mode",
        "Single member",
        "Forwarded-name mapping",
        "Routing overrides"
      ]
    },
    {
      "entity": "route-member",
      "shows": [
        "Route",
        "Connection",
        "Group name",
        "Status",
        "Priority",
        "Weight",
        "Forwarded-name mapping",
        "Price layer",
        "Health",
        "Cooldown",
        "Manual intent",
        "Automatic origin"
      ],
      "collects": [
        "Route",
        "Connection",
        "Group name",
        "Status",
        "Priority",
        "Weight",
        "Forwarded-name mapping",
        "Price layer",
        "Manual intent"
      ]
    },
    {
      "entity": "model-metadata",
      "shows": [
        "Model name",
        "Vendor",
        "Description",
        "Context limit",
        "Modalities",
        "Reasoning",
        "Price layer",
        "Classification source"
      ],
      "collects": [
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
      "shows": [
        "Model name",
        "Endpoints",
        "Input modalities",
        "Output modalities",
        "Image formats",
        "Image limits",
        "Classification source"
      ]
    },
    {
      "entity": "unification-batch",
      "shows": [
        "Canonical name",
        "Changes",
        "Original snapshots",
        "Created at",
        "Undo progress"
      ],
      "collects": [
        "Canonical name"
      ]
    },
    {
      "entity": "connection",
      "shows": [
        "Name",
        "Status",
        "Model snapshot"
      ]
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



# Models

The outward-model subject presents routes, bindings, catalog facts, whole-layer pricing and reversible name-unification history.
