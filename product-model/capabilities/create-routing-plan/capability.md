---
{
  "availability": [
    {
      "place": "console::personal"
    }
  ],
  "domain": "models",
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/MemberModelsPage.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/member/RouteOrderDialog.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/team_access.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/domain/team.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_resources.go#savePlan"
    }
  ]
}
---




# Create routing plan

Create an owned named plan subject to the named-plan limit.

A new owned named plan exists with its initial arrangements.
