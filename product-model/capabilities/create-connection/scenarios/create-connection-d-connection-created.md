---
{
  "kind": "primary",
  "routes": {
    "main": "D connection created"
  },
  "steps": [
    {
      "text": "Supply destination, protocol, name and credential information.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "For a new normalized upstream address establish the Site, its enabled Upstream API key and enabled Connection; an existing matching site uses the separate reuse branch.",
      "kind": "product",
      "entities": [
        {
          "entity": "site",
          "effect": "creates",
          "facts": [
            "Name",
            "Base address",
            "Platform",
            "Status",
            "Call policy"
          ]
        },
        {
          "entity": "upstream-api-key",
          "effect": "creates",
          "facts": [
            "Site",
            "Credential",
            "Secret availability",
            "Status",
            "Model restrictions",
            "Priority",
            "Discovery evidence",
            "Remote token reference"
          ],
          "to": "Enabled",
          "with": "site"
        },
        {
          "entity": "connection",
          "effect": "creates",
          "facts": [
            "Name",
            "Site",
            "Credential association",
            "Base address",
            "Protocol",
            "Status",
            "Priority",
            "Weight",
            "Model snapshot",
            "Model sync mode",
            "Routing controls",
            "Forwarding settings",
            "Connectivity observations",
            "Group name"
          ],
          "to": "Enabled",
          "with": "site"
        }
      ],
      "contexts": {
        "main": {
          "place": "management-api::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "The registered creation operation saves the supplied forwarding destination and returns it; later console verification is not part of this API call.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "management-api::administration"
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
    }
  ]
}
---









# Create connection connection created

## Trigger

Supply destination, protocol, name and credential information.

## Outcome

The registered creation operation saves the supplied connection and returns it; later console verification is not part of this API call.

## Edge cases

- A matching normalized address reuses its existing Site identity instead of creating a duplicate; the new credential and connection are then retained on that site. Failure while saving a new connection cleans up its newly created credential and, if newly created for this attempt, site.
