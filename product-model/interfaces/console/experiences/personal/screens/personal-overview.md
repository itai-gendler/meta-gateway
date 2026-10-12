---
{
  "entities": [
    {
      "entity": "account",
      "shows": [
        "Login name",
        "Display name",
        "Token limit",
        "Tokens used",
        "Money limit",
        "Money used"
      ]
    },
    {
      "entity": "account-token",
      "shows": [
        "Name",
        "Credential hint",
        "Status",
        "Model restrictions",
        "IP restrictions",
        "Expiry",
        "Tokens used",
        "Account"
      ]
    },
    {
      "entity": "usage-record",
      "shows": [
        "Time",
        "Model",
        "Tokens",
        "Recorded cost",
        "Status"
      ]
    },
    {
      "entity": "money-display-settings",
      "shows": [
        "Symbol",
        "Rate"
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




# Personal overview

The current Account overview presents owned access, budgets and recorded usage aggregates.
