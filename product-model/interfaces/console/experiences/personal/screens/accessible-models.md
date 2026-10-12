---
{
  "entities": [
    {
      "entity": "route",
      "shows": [
        "Model name/pattern",
        "Status"
      ]
    },
    {
      "entity": "route-member",
      "shows": [
        "Route",
        "Connection",
        "Group name",
        "Status",
        "Priority",
        "Weight"
      ]
    },
    {
      "entity": "connection",
      "shows": [
        "Name",
        "Site",
        "Protocol",
        "Status"
      ]
    },
    {
      "entity": "model-metadata",
      "shows": [
        "Model name",
        "Vendor",
        "Description",
        "Context limit",
        "Modalities",
        "Reasoning",
        "Price layer",
        "Classification source"
      ]
    },
    {
      "entity": "model-capability",
      "shows": [
        "Model name",
        "Endpoints",
        "Input modalities",
        "Output modalities",
        "Image formats",
        "Image limits",
        "Classification source"
      ]
    },
    {
      "entity": "routing-plan",
      "shows": [
        "Name",
        "Account",
        "Default selection",
        "Model arrangements",
        "Token selections"
      ],
      "collects": [
        "Name",
        "Model arrangements"
      ]
    },
    {
      "entity": "account-token",
      "collects": [
        "Routing plan"
      ]
    }
  ],
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
    }
  ]
}
---



# Accessible models

The permitted-model subject presents current catalog grants and owned personal upstream arrangements.
