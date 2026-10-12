---
{
  "kind": "primary",
  "routes": {
    "main": "R account observed"
  },
  "steps": [
    {
      "text": "Request a remote user credential check.",
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
      "text": "Consult the Upstream account. Consult the Site.",
      "kind": "condition",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "reads",
          "facts": [
            "Site",
            "Credential",
            "Cookie",
            "Credential availability",
            "Authentication mode",
            "Platform identity",
            "Status"
          ]
        },
        {
          "entity": "site",
          "effect": "reads",
          "facts": [
            "Platform",
            "Status"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Save changes to the Upstream account.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Platform identity"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Record the Connection credential-check success and clear its prior remote rate-limit pause.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Connectivity observations",
            "Routing controls"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Return the observed remote quota and user information; retain the credential identity and connectivity verdict, without booking these values as gateway cost.",
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
      "target": "internal/account/service.go#Probe"
    }
  ]
}
---










# Check upstream account account observed

## Trigger

Request an upstream Account check.

## Outcome

Observed remote quota and user information is returned; the remote identity and connection verdict are retained. These values do not become recorded gateway cost.
