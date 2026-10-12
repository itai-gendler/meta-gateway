---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "request-log-entry",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        },
        {
          "place": "console::personal"
        }
      ],
      "facts": [
        "Request",
        "Attempt",
        "Time",
        "Token label",
        "Model",
        "Endpoint",
        "Status",
        "Latency",
        "Tokens",
        "Error category"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "related": [
        {
          "verb": "has",
          "entity": "account"
        },
        {
          "verb": "owns",
          "entity": "member"
        }
      ],
      "when": [
        {
          "entity": "team-settings",
          "fact": "Usage visibility",
          "is": true
        }
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



# Deployment administrator, Owner or the related Member may read Request log entry

Deployment administrator and Owner read common and routing/upstream request facts. A related Member reads only its own Account-attributed common projection while usage visibility is enabled. Routing and upstream disclosure are closed in the personal console.
