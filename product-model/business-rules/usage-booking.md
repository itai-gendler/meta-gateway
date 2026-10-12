---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "call-chat-completions"
    },
    {
      "type": "capability",
      "id": "call-completions"
    },
    {
      "type": "capability",
      "id": "call-responses"
    },
    {
      "type": "capability",
      "id": "call-messages"
    },
    {
      "type": "capability",
      "id": "create-embedding"
    },
    {
      "type": "capability",
      "id": "count-message-tokens"
    },
    {
      "type": "capability",
      "id": "generate-image"
    },
    {
      "type": "capability",
      "id": "edit-image"
    },
    {
      "type": "capability",
      "id": "vary-image"
    },
    {
      "type": "capability",
      "id": "send-message"
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
      "type": "entity",
      "id": "usage-record"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/relay.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_health.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_keypool.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/usage.go"
    }
  ]
}
---



# Only recognized positive usage is booked with transactional counters and log backfill

Positive recognized total usage is required, falling back to prompt plus completion where implemented. Missing usage skips the per-request charge too. The transaction stores usage, increments Token/group/Account counters and backfills request-log information. There is no blanket successful-status-only booking rule. A failed booking is logged without a guarantee that the already executing request fails. A qualifying interrupted 2xx text stream with output bytes and no valid usage may estimate completion as floor(bytes/4), prompt zero; image endpoints disable this estimation. No image count or Base64 size is invented as token usage. Local edits and staff diagnostic calls do not become regular billed requests.
