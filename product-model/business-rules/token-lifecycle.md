---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-token"
    },
    {
      "type": "capability",
      "id": "edit-token"
    },
    {
      "type": "capability",
      "id": "enable-token"
    },
    {
      "type": "capability",
      "id": "disable-token"
    },
    {
      "type": "capability",
      "id": "reveal-token"
    },
    {
      "type": "capability",
      "id": "rotate-token"
    },
    {
      "type": "capability",
      "id": "delete-token"
    },
    {
      "type": "entity",
      "id": "system-token"
    },
    {
      "type": "entity",
      "id": "account-token"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Keys.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_keys.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/downstream_key.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    }
  ]
}
---



# Token creation slots, revelation and deletion follow their distinct credential contracts

Creation/reveal/rotation/deletion: disabled Tokens count toward limit, neutralized ones do not; rotation invalidates cache; own neutralization retains attribution; custom hash-only credentials can be valid without revealable plaintext
