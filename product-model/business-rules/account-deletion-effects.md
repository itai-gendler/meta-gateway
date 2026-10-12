---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "delete-account"
    },
    {
      "type": "entity",
      "id": "account"
    },
    {
      "type": "entity",
      "id": "account-token"
    },
    {
      "type": "entity",
      "id": "routing-plan"
    },
    {
      "type": "entity",
      "id": "account-session"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/panels/MembersPanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_members.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_admin.go"
    }
  ]
}
---



# Owner row protection does not shield unfiltered dependent cleanup or invalidate cached Token authority

Final Account deletion protects the Owner row. The requested identity set reaches dependent cleanup before that final filter, so an Owner ID can neutralize its retained Token authority and remove sessions, plans, identities and recovery authority while the Account survives. This path does not invalidate the Token cache. A warm owner-key snapshot can still authenticate when current Account/mode/policy/selected-plan/scope/quota checks pass; no cache TTL was observed. A removed non-owner Account fails fresh Account lookup.
