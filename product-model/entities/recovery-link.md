---
{
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



# Recovery link

Account-bound bearer authority for replacing a forgotten password.

## Information kept

- **Code credential** — the presented bearer code; persistence retains its hash and issuance returns plaintext only once.
- **Account** — the associated Account, without implying current credential eligibility.
- **Validity** — the code expiration information, checked when its authority is presented.
- **Consumption** — whether the recovery authority has already replaced the password.
- **Revocation** — whether further use of the code has been explicitly revoked.
