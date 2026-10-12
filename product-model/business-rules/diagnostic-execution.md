---
{
  "appliesTo": [
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
      "type": "capability",
      "id": "send-message"
    },
    {
      "type": "entity",
      "id": "connection"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/Playground.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/ImageStudio.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/runner.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/workbenchState.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/try.go"
    }
  ]
}
---



# Diagnostic execution has different routing and downstream-booking effects from member calls

Diagnostic/direct-model calls have distinct pin/channel, health, and downstream-booking behavior; no downstream booking does not mean free upstream consumption
