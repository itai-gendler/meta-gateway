---
{
  "kind": "validation",
  "routes": {
    "main": "R invalid schedule"
  },
  "steps": [
    {
      "text": "Supply check-in enablement and schedule choices.",
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
      "text": "The supported check-in schedule input is invalid.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      }
    },
    {
      "text": "The schedule change is rejected without applying the invalid setting.",
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








# Change check in settings invalid schedule

## Trigger

The supported check-in schedule input is invalid.

## Outcome

The schedule change is rejected without applying the invalid setting.
