---
{
  "id": "meta-gateway",
  "summary": "Self-hosted AI gateway and console for upstream connections, model routing, scoped access and recorded usage.",
  "category": "ai-gateway",
  "tags": [
    "llm",
    "routing",
    "admin-console"
  ],
  "authors": [
    {
      "name": "ZiChuanLan"
    }
  ],
  "license": "MIT",
  "languages": [
    "en",
    "zh-CN"
  ],
  "limitations": [
    "Upstream execution, identity-provider exchange, native check-in and WebDAV success depend on the configured external systems.",
    "Recorded cost is the gateway configured charge, not a verified upstream invoice.",
    "Browser workbench history is origin-scoped and survives sign-out."
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/router.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "cmd/server/main.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    }
  ]
}
---



# Meta Gateway

Meta Gateway connects downstream AI clients to configured upstream connections and model routes. Operators manage credentials, discovery, routing, scoped Tokens, Account policies and operational records. Members use their permitted models, personal arrangements and workbench. The Product records recognized usage and configured charges, exchanges connection settings, and creates snapshots for offline restoration.

## Intent

Downstream AI clients multiply while upstream sites differ in model names, scatter quotas and each fail on their own. Meta Gateway lets a self-hoster mount every upstream connection once, so each downstream client needs one address and one Token, and passes requests through without rewriting their meaning.
