---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "send-message"
    },
    {
      "type": "capability",
      "id": "probe-chat"
    },
    {
      "type": "capability",
      "id": "edit-message"
    },
    {
      "type": "capability",
      "id": "resubmit-message"
    },
    {
      "type": "capability",
      "id": "regenerate-answer"
    },
    {
      "type": "capability",
      "id": "stop-answer"
    },
    {
      "type": "capability",
      "id": "delete-message"
    },
    {
      "type": "capability",
      "id": "clear-conversation"
    },
    {
      "type": "entity",
      "id": "conversation"
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



# Conversation history is origin-scoped and distinguishes Save from inference resubmission

History is retained in the browser-origin namespace shared by use of that origin, with no Account ownership or sign-out clearing. Save edits content only and retains later turns. Resubmit edits, truncates later turns and performs inference. Regenerate replaces the selected assistant answer while retaining later turns. User-turn deletion also removes its immediately adjacent answer. Stop retains partial content/reasoning and a stopped marker; clear aborts and empties turns. Approximate 100-turn/512-KB trimming can keep one oversized turn and storage can fall back to memory. Persisted streaming markers normalize rather than promising resumable streams.
