---
{
  "kind": "primary",
  "routes": {
    "main": "R role changed"
  },
  "steps": [
    {
      "text": "Select a unprotected local login identity and its replacement held role.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    },
    {
      "text": "Consult the Account.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Login name"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner",
      "text": "When promoting, remove Member and establish Administrator, invalidate the Account session and advance the Account revision.",
      "kind": "product",
      "entities": [
        {
          "entity": "member",
          "effect": "removes"
        },
        {
          "entity": "administrator",
          "effect": "creates",
          "facts": [
            "Account association"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Session revision"
          ]
        },
        {
          "entity": "account-session",
          "effect": "removes"
        }
      ]
    },
    {
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner",
      "text": "Alternatively, when demoting, remove Administrator and establish Member, invalidate the Account session and advance the Account revision.",
      "kind": "product",
      "entities": [
        {
          "entity": "administrator",
          "effect": "removes"
        },
        {
          "entity": "member",
          "effect": "creates",
          "facts": [
            "Account association"
          ]
        },
        {
          "entity": "account",
          "effect": "changes",
          "facts": [
            "Session revision"
          ]
        },
        {
          "entity": "account-session",
          "effect": "removes"
        }
      ]
    },
    {
      "text": "The previous role association is dropped, the replacement established, and individual-update session invalidation occurs.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration::members"
        }
      },
      "actor": "owner"
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











# Change account role role changed

## Trigger

Select a non-owner Account and its replacement held role.

## Outcome

The previous role association is dropped, the replacement established, and individual-update session invalidation occurs.

## Decision points

### Replacement role

Which non-owner role is requested?

- Administrator requested for Member → replace the Member association with Administrator and invalidate sessions.
- Member requested for Administrator → replace the Administrator association with Member and invalidate sessions.
- Unchanged held role → retain its association and apply individual-update session invalidation.
