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



# Credit code

Bearer authority adding token or monetary face values to the redeeming Account.

## Information kept

- **Code credential** — the presented bearer code; persistence retains its hash and issuance returns plaintext only once.
- **Label** — the staff-facing label identifying the code.
- **Staff management audience** — the Member or Administrator audience restricting staff issuance, inventory and revocation; redemption assigns no role.
- **Token grant** — the token face value added to an Account total on successful redemption.
- **Money grant** — the monetary face value added to an Account total on successful redemption.
- **Validity** — the code expiration information, checked when its authority is presented.
- **Use limit** — the maximum permitted number of successful code uses.
- **Uses** — the number of successful uses already consumed.
- **Redemptions** — the Accounts that have already redeemed this credit code.
- **Revocation** — whether further use of the code has been explicitly revoked.
