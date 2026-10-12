---
{
  "kind": "edge",
  "routes": {
    "main": "R already running"
  },
  "steps": [
    {
      "text": "Request or schedule native check-in.",
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
      "text": "The native check-in credential already has an active run.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      }
    },
    {
      "text": "The already-running outcome is returned and another concurrent check-in is not started.",
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








# Run check in already running

## Trigger

The native check-in credential already has an active run.

## Outcome

The already-running outcome is returned and another concurrent check-in is not started.
