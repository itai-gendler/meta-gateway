---
{
  "appliesTo": [
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
    },
    {
      "type": "entity",
      "id": "account"
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



# Valid code consumption is bounded and credit face values add to retained totals

Code consumption and Account effects: validity/use limits; transactional credit uniqueness/use increment; face values add to totals while used counters remain
