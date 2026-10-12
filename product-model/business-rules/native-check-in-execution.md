---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-check-in-settings"
    },
    {
      "type": "capability",
      "id": "run-check-in"
    },
    {
      "type": "entity",
      "id": "upstream-account"
    },
    {
      "type": "entity",
      "id": "site"
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



# Native check-in uses supported eligible credentials and serializes each active run

Supported adapter, enabled relevant Site/credential, credential/cookie availability, module/schedule gates, serialization, distinguished remote failures
