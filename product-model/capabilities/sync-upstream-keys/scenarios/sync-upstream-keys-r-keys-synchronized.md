---
{
  "kind": "primary",
  "routes": {
    "main": "R keys synchronized"
  },
  "steps": [
    {
      "text": "Request upstream key synchronization.",
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
            "Credential",
            "Cookie",
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
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner",
      "text": "When the remote user identity is missing and the self lookup succeeds, retain the observed Upstream account platform identity.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Platform identity"
          ]
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner",
      "text": "For each usable new remote secret establish the Upstream API key with its observed enabled choice; the enabled and disabled branches are alternatives.",
      "kind": "product",
      "entities": [
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
          "as": "new-enabled"
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
          "to": "Disabled",
          "as": "new-disabled"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner",
      "text": "Reuse the same-secret Upstream API key and refresh its observed remote token reference without overwriting its retained enabled choice.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-api-key",
          "effect": "changes",
          "facts": [
            "Remote token reference"
          ],
          "as": "reused-key"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner",
      "text": "After a successful comparison against the full bounded remote list, remove an orphaned Upstream API key only if it has a known positive remote identity. Clear each Connection association that pointed at a removed key.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-api-key",
          "effect": "removes",
          "as": "orphaned-key-enabled",
          "from": "Enabled"
        },
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Credential association"
          ],
          "as": "requested-connection"
        },
        {
          "entity": "upstream-api-key",
          "effect": "removes",
          "as": "orphaned-key-disabled",
          "from": "Disabled"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner",
      "text": "When attachment is requested and the Connection has no API-key binding, attach the first usable imported or reused key. Retain an existing API-key binding.",
      "kind": "product",
      "entities": [
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Credential association"
          ],
          "as": "requested-connection"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::connections"
        }
      },
      "actor": "owner",
      "text": "When group splitting is requested, establish an enabled missing group Connection with the inherited base address and protocol hint, or update the existing Connection credential, group and generic display name. Keep existing routing and forwarding settings.",
      "kind": "product",
      "entities": [
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
          "as": "new-enabled-group"
        },
        {
          "entity": "connection",
          "effect": "changes",
          "facts": [
            "Credential association",
            "Name",
            "Group name"
          ],
          "as": "existing-group"
        }
      ]
    },
    {
      "text": "Observed remote keys are reconciled into managed key records.",
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
      "target": "internal/account/service.go#SyncKeys"
    }
  ]
}
---













# Sync upstream keys keys synchronized

## Trigger

Request upstream key synchronization.

## Outcome

Observed remote keys are reconciled into managed key records.

## Edge cases

- Import defaults to 20 keys and is capped at 100. A successful full-list comparison (up to 100) can prune known remote-ID-bearing keys, while manually pasted keys and an empty initial list are retained. Attachment is optional and keeps an existing API-key association. Group splitting is opt-in, uses the first enabled key per group and creates enabled default destinations; existing destinations retain routing and forwarding settings.

## Decision points

### Remote secret and retained records

Is each observed usable secret already retained?

- New usable secret → create a key with its observed Enabled or Disabled choice.
- Matching secret → reuse the row, refresh observed name/group/remote identity and retain the saved status.
- Masked unrevealable secret → skip that item and report the skipped category.
