---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "refresh-connection-models"
    },
    {
      "type": "capability",
      "id": "preview-connection-models"
    },
    {
      "type": "capability",
      "id": "add-route-member"
    },
    {
      "type": "capability",
      "id": "disable-route-member"
    },
    {
      "type": "capability",
      "id": "remove-route-member"
    },
    {
      "type": "entity",
      "id": "discovered-model"
    },
    {
      "type": "entity",
      "id": "connection"
    },
    {
      "type": "entity",
      "id": "route-member"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Channels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/ChannelModels.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_connections.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_credentials.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/discovery.go"
    }
  ]
}
---



# Manual discovery preserves candidates while Auto adopts and unchecking follows binding origin

Manual candidate refresh versus automatic adoption; disappearance does not generally delete bindings; manual plain uncheck removes; automatic/aliased bindings can remain parked; preview persists none
