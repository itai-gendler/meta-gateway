---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "check-in-log",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "management-api::administration"
        }
      ],
      "facts": [
        "Site",
        "Credential",
        "Trigger",
        "Time",
        "Outcome",
        "Category",
        "Reward"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
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



# Deployment administrator, Owner may read Check in log

Deployment administrator and Owner read native check-in history, including the recorded trigger, credential/Site, outcome/category and reward observations.
