---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-code"
    },
    {
      "type": "capability",
      "id": "issue-recovery-link"
    },
    {
      "type": "capability",
      "id": "register-account"
    },
    {
      "type": "capability",
      "id": "recover-password"
    },
    {
      "type": "capability",
      "id": "redeem-account-credit"
    },
    {
      "type": "entity",
      "id": "invitation-code"
    },
    {
      "type": "entity",
      "id": "credit-code"
    },
    {
      "type": "entity",
      "id": "recovery-link"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/team/CodePanel.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_codes.go"
    }
  ]
}
---



# Code authority is hashed and normalized without making credit policy-scoped

Code issuance/credential handling: hashed authority, issuance-only plaintext, normalized short codes, compatible legacy tokens; credit Policy placeholder is not credit policy scope
