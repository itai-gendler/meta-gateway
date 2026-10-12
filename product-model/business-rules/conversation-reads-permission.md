---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "conversation",
      "effect": "reads",
      "contexts": [
        {
          "place": "console::administration"
        },
        {
          "place": "console::personal"
        }
      ],
      "facts": [
        "Turns",
        "Model",
        "Parameters"
      ]
    }
  ],
  "permits": [
    {
      "actors": [
        "deployment-administrator",
        "owner"
      ]
    },
    {
      "actors": [
        "member"
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/Playground.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/ImageStudio.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/runner.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/workbench/workbenchState.ts"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/try.go"
    }
  ]
}
---



# Deployment administrator, Owner or Member may read Conversation Turns, Model, Parameters

Deployment administrator and Owner use diagnostic conversation history; Member uses the personal workbench in the current browser context. The history belongs to the browser origin, remains through sign-out and is not promised to be isolated by Account.
