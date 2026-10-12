---
{
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




# Usage record

Persisted recognized usage and configured charge attributed to a request, Token and optionally Account.

## Information kept

- **Request** — the request identity associating attempts, usage and live activity.
- **Time** — the instant the recognized usage was booked.
- **Account attribution** — the Account to which the operation was attributed, if applicable.
- **Token attribution** — the downstream Token to which the operation was attributed.
- **Model** — the requested outward model associated with this usage.
- **Endpoint** — the operation family used by the request.
- **Tokens** — recognized input/output/total usage and applicable interrupted-text estimation.
- **Cache tokens** — recognized cache-creation and cache-read usage.
- **Recorded cost** — the persisted configured gateway charge, not verified upstream expenditure.
- **Status** — the observed request status associated with the recorded recognized usage.
