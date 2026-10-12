---
{
  "kind": "primary",
  "result": "achieved",
  "routes": {
    "setup": "First-access setup"
  },
  "steps": [
    {
      "text": "Choose the Manual model-sync default for first access.",
      "kind": "actor",
      "actor": "deployment-administrator",
      "capability": "change-runtime-settings",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Save changes to the Runtime settings.",
      "kind": "product",
      "actor": "deployment-administrator",
      "capability": "change-runtime-settings",
      "entities": [
        {
          "entity": "runtime-settings",
          "effect": "changes",
          "facts": [
            "Editable values",
            "Effective values",
            "Sources",
            "Override"
          ]
        }
      ],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Supply a new upstream destination, name and upstream key.",
      "kind": "actor",
      "actor": "deployment-administrator",
      "capability": "create-connection",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Establish the Site. Establish the Upstream API key in Enabled state. Establish the Connection in Enabled state.",
      "kind": "product",
      "actor": "deployment-administrator",
      "capability": "create-connection",
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
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Carry the same person to model verification before credential issuance.",
      "kind": "product",
      "actor": "deployment-administrator",
      "capability": "create-connection",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Refresh the saved forwarding destination candidate snapshot.",
      "kind": "actor",
      "actor": "deployment-administrator",
      "capability": "refresh-connection-models",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Save changes to the Connection. Establish the Discovered model.",
      "kind": "product",
      "actor": "deployment-administrator",
      "capability": "refresh-connection-models",
      "entities": [
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Model snapshot"
          ]
        },
        {
          "entity": "discovered-model",
          "effect": "creates",
          "facts": [
            "Name",
            "Connection",
            "Credential evidence",
            "Observed at"
          ]
        }
      ],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Supply first downstream credential settings.",
      "kind": "actor",
      "actor": "deployment-administrator",
      "capability": "create-token",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Issue an enabled privileged downstream credential and reveal its new authority.",
      "kind": "product",
      "actor": "deployment-administrator",
      "capability": "create-token",
      "entities": [
        {
          "entity": "system-token",
          "effect": "creates",
          "facts": [
            "Name",
            "Credential",
            "Credential hint",
            "Status",
            "Scopes",
            "Model restrictions",
            "Denylist",
            "IP restrictions",
            "Expiry",
            "Token group",
            "Route group",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used"
          ],
          "to": "Enabled"
        }
      ],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Finish the carried setup process.",
      "kind": "actor",
      "actor": "deployment-administrator",
      "capability": "create-token",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::setup"
        }
      }
    },
    {
      "text": "Carry the same person to the gateway overview.",
      "kind": "product",
      "actor": "deployment-administrator",
      "capability": "create-token",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::gateway-overview"
        }
      }
    },
    {
      "text": "Read the overview after configuration is retained.",
      "kind": "actor",
      "actor": "deployment-administrator",
      "capability": "read-overview",
      "entities": [],
      "contexts": {
        "setup": {
          "place": "console::administration::gateway-overview"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Exchange.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/SetupWizard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/exchange.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/exchange/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/webdav.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/webdavsync/service.go"
    }
  ]
}
---







# Prepare first access as Deployment administrator

## Trigger

The Deployment administrator enters first-access Setup; the Owner case uses an existing Owner association.

## Outcome

Defaults, connection authority and first System token are retained, and the same administrator reaches the overview. This achieved path creates a new upstream destination and refreshes its snapshot; external availability remains separately observed.
