---
{
  "availability": [
    {
      "place": "console::personal"
    }
  ],
  "domain": "account",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/AccountPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_preferences.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go#redeemCredit"
    }
  ]
}
---



# Change request preferences

Save permitted failover inheritance/on/off and an optional retry cap.

The saved preferences narrow applicable regular Account-token forwarding.
