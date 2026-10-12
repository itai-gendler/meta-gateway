---
{
  "kind": "primary",
  "routes": {
    "main": "R check ins listed"
  },
  "steps": [
    {
      "text": "Read check-in history.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the check-in record.",
      "kind": "condition",
      "entities": [
        {
          "entity": "check-in-log",
          "effect": "reads",
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
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      },
      "actor": "owner"
    },
    {
      "text": "upstream destination/credential, trigger, time, outcome/category and reward are presented.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      },
      "actor": "owner"
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








# Browse check in history check ins listed

## Trigger

Read check-in history.

## Outcome

Site/credential, trigger, time, outcome/category and reward are presented.
