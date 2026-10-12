---
{
  "kind": "validation",
  "routes": {
    "main": "R account ineligible"
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
      "text": "The resolved relevant upstream destination/user credential or adapter is not eligible for this remote user credential operation.",
      "kind": "condition",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::checkins"
        }
      }
    },
    {
      "text": "The operation returns its eligibility/category result without a remote local profile action; forwarding destination enabled state alone does not establish eligibility.",
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








# Run check in account ineligible

## Trigger

The resolved relevant Site/user credential or adapter is not eligible for this upstream Account operation.

## Outcome

The operation returns its eligibility/category result without a remote Account action; Connection enabled state alone does not establish eligibility.
