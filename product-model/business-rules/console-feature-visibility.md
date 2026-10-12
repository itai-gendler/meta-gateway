---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-models"
    },
    {
      "type": "capability",
      "id": "browse-request-logs"
    },
    {
      "type": "capability",
      "id": "read-overview"
    },
    {
      "type": "capability",
      "id": "browse-routing-plans"
    },
    {
      "type": "capability",
      "id": "reorder-upstreams"
    },
    {
      "type": "entity",
      "id": "team-settings"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Logs.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_usage.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/operations.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/livetrace_handler.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/proxylog.go"
    }
  ]
}
---



# Role-specific sources and visibility settings do not imply blanket endpoint parity

Role-specific data sources/projections; usage and routing visibility affect their inspected surfaces without inferred blanket endpoint denial
