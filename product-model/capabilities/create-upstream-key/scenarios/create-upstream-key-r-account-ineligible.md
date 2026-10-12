---
{
  "kind": "validation",
  "routes": {
    "main": "R account ineligible"
  },
  "steps": [
    {
      "text": "Supply the supported remote-key creation choice.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The resolved relevant upstream destination/user credential or adapter is not eligible for this remote user credential operation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      }
    },
    {
      "text": "The operation returns its eligibility/category result without a remote local profile action; forwarding destination enabled state alone does not establish eligibility.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/account/service.go#CreateKey"
    }
  ]
}
---











# Create upstream key account ineligible

## Trigger

The resolved relevant Site/user credential or adapter is not eligible for this upstream Account operation.

## Outcome

The operation returns its eligibility/category result without a remote Account action; Connection enabled state alone does not establish eligibility.
