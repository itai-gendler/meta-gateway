---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "capability",
      "id": "call-completions"
    },
    {
      "type": "capability",
      "id": "call-responses"
    },
    {
      "type": "capability",
      "id": "call-messages"
    },
    {
      "type": "capability",
      "id": "create-embedding"
    },
    {
      "type": "capability",
      "id": "count-message-tokens"
    },
    {
      "type": "capability",
      "id": "generate-image"
    },
    {
      "type": "capability",
      "id": "edit-image"
    },
    {
      "type": "capability",
      "id": "vary-image"
    },
    {
      "type": "capability",
      "id": "probe-chat"
    },
    {
      "type": "capability",
      "id": "probe-image-generation"
    },
    {
      "type": "capability",
      "id": "probe-image-edit"
    },
    {
      "type": "capability",
      "id": "test-connection-model"
    },
    {
      "type": "entity",
      "id": "request-log-entry"
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



# Mapped request operations record actual attempts and outcomes

Mapped request/probe operations and bare Request log entry record actual attempts/outcomes/routing metadata; no universal guarantee about untrusted upstream error strings
