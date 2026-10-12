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
      "target": "internal/domain/capability.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/model_capabilities.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_model_bootstrap.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/modelcatalog/service.go"
    }
  ],
  "domain": "models"
}
---



# Model capability

Retained callable endpoint and modality information used to plan model requests.

## Information kept

- **Model name** — the outward model name whose request protocol is described.
- **Endpoints** — the callable endpoint families retained for this model.
- **Input modalities** — the supported model input kinds.
- **Output modalities** — the supported model output kinds.
- **Image formats** — the supported image input encodings, including JSON or multipart where provided.
- **Image limits** — the retained maximum input-image count and supported size choices.
- **Classification source** — manual, local classification or external catalog origin controlling overwrite behavior.
