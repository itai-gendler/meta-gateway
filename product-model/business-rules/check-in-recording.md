---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "run-check-in"
    },
    {
      "type": "entity",
      "id": "check-in-log"
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



# Native check-in execution records its trigger and observed outcome

Manual/scheduled native execution and bare Check-in log record trigger, credential/site, outcome/category, reward
