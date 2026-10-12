---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "browse-request-logs"
    },
    {
      "type": "entity",
      "id": "request-log-entry"
    },
    {
      "type": "entity",
      "id": "usage-record"
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



# Member requests are an Account-scoped common projection of the same log

Account-scoped grouping/safe common projection and recorded-cost join; one underlying log Entity
