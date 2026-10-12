---
{
  "availability": [
    {
      "place": "console::administration"
    },
    {
      "place": "management-api::administration"
    }
  ],
  "domain": "members-and-invitations",
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
    },
    {
      "kind": "doc",
      "role": "context",
      "target": "docs/reference/admin-api.md"
    }
  ]
}
---



# Adjust account quota

Set a managed Account token and monetary total budget.

The totals are saved; zero is unlimited, and already-used counters are retained.
