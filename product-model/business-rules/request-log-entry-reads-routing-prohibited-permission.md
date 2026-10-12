---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "request-log-entry",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::personal"
        }
      ],
      "facts": [
        "Routing details",
        "Upstream details"
      ]
    }
  ],
  "permits": [],
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



# No Actor may read Request log entry Routing details, Upstream details in the personal console

Deployment administrator and Owner read common and routing/upstream request facts. A related Member reads only its own Account-attributed common projection while usage visibility is enabled. Routing and upstream disclosure are closed in the personal console.
