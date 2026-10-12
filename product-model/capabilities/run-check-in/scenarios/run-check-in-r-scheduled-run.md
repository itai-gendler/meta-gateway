---
{
  "kind": "primary",
  "routes": {
    "main": "R scheduled run"
  },
  "steps": [
    {
      "text": "The configured schedule is due.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      },
      "unattended": true
    },
    {
      "text": "Consult the Upstream account. Consult the Site. Consult the Runtime settings.",
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
            "Status",
            "Check-in setting"
          ]
        },
        {
          "entity": "site",
          "effect": "reads",
          "facts": [
            "Platform",
            "Status"
          ]
        },
        {
          "entity": "runtime-settings",
          "effect": "reads",
          "facts": [
            "Effective values"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      }
    },
    {
      "text": "Save changes to the Upstream account.",
      "kind": "product",
      "entities": [
        {
          "entity": "upstream-account",
          "effect": "changes",
          "facts": [
            "Account observations"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      }
    },
    {
      "text": "The observed success/failure/reward is recorded; concurrent runs for the same credential are serialized.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Checkins.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/checkin.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/checkin/service.go"
    }
  ]
}
---








# Run check in scheduled run

## Trigger

The configured schedule becomes due for run native check-in through a supported resolved upstream user credential.

## Outcome

The observed success/failure/reward is recorded; concurrent runs for the same credential are serialized.
