---
{
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
  ],
  "domain": "workbench"
}
---




# Conversation

Local browser-origin conversation history shared by use of that origin, independent of Account ownership.

## Information kept

- **Turns** — ordered user/assistant content, reasoning, completion/error/stopped information and local edit drafts.
- **Model** — the currently retained model choice for the browser conversation.
- **Parameters** — the model/request parameters retained with the browser-origin conversation.
