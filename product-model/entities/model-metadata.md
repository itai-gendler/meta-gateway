---
{
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/model_metadata.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_model_catalog.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/modelcatalog/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_health.go"
    }
  ],
  "domain": "models",
  "relations": [
    {
      "entity": "model-capability",
      "verb": "describes",
      "cardinality": "one-to-one"
    }
  ]
}
---



# Model metadata

Retained catalog, classification and whole-layer pricing information for one model name.

## Information kept

- **Model name** — the outward model name identifying metadata, capability or pricing information.
- **Vendor** — the model vendor information retained by metadata.
- **Description** — the model description retained by metadata.
- **Context limit** — the model context-size information.
- **Modalities** — the retained model input/output modality information.
- **Reasoning** — the retained reasoning-capability information.
- **Price layer** — flat token/cache/request prices, optional tiers and time windows, selected as one whole layer.
- **Classification source** — manual, local classification or external catalog origin controlling overwrite behavior.
