---
{
  "entities": [
    {
      "entity": "live-request",
      "shows": [
        "Request",
        "Model",
        "Endpoint",
        "Token label",
        "Start time",
        "Progress",
        "Status",
        "Interruption"
      ],
      "collects": [
        "Request"
      ]
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



# Live requests

Current in-memory request progress and the result of a selected interruption.
