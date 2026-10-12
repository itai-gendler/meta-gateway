---
{
  "entities": [
    {
      "entity": "upstream-account",
      "shows": [
        "Site",
        "Credential availability",
        "Check-in setting"
      ],
      "collects": [
        "Check-in setting"
      ]
    },
    {
      "entity": "check-in-log",
      "shows": [
        "Site",
        "Credential",
        "Trigger",
        "Time",
        "Outcome",
        "Category",
        "Reward"
      ]
    },
    {
      "entity": "runtime-settings",
      "collects": [
        "Editable values"
      ]
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



# Checkins

The native check-in subject presents enablement, schedule input and recorded manual/scheduled outcomes.
