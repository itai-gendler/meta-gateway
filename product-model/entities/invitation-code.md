---
{
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
  ],
  "domain": "codes"
}
---



# Invitation code

Bearer authority establishing a new Account and its assigned fixed role.

## Information kept

- **Code credential** — the presented bearer code; persistence retains its hash and issuance returns plaintext only once.
- **Label** — the staff-facing label identifying the code.
- **Assigned role** — the fixed role established when the invitation is accepted.
- **Policy** — the selected access policy governing the Account or invitation assignment.
- **Initial tokens** — the token budget assigned to a newly invited Account.
- **Initial money** — the monetary budget assigned to a newly invited Account.
- **Validity** — the code expiration information, checked when its authority is presented.
- **Use limit** — the maximum permitted number of successful code uses.
- **Uses** — the number of successful uses already consumed.
- **Revocation** — whether further use of the code has been explicitly revoked.
