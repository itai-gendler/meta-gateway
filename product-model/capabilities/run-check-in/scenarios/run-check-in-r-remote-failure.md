---
{
  "kind": "edge",
  "routes": {
    "main": "R remote failure"
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
      "text": "The configured remote check-in, key or WebDAV operation fails.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      }
    },
    {
      "text": "The distinguished remote failure is returned and applicable last-result information retained; success is not fabricated.",
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








# Run check in remote failure

## Trigger

The configured remote check-in, key or WebDAV operation fails.

## Outcome

The distinguished remote failure is returned and applicable last-result information retained; success is not fabricated.
