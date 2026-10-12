---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "export-connections"
    },
    {
      "type": "capability",
      "id": "import-connections"
    },
    {
      "type": "entity",
      "id": "connection"
    },
    {
      "type": "entity",
      "id": "site"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/Exchange.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/features/SetupWizard.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/exchange.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/exchange/service.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/webdav.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/webdavsync/service.go"
    }
  ]
}
---



# Supported connection exchange distinguishes per-item and document failures

Parsing distinguishes invalid/unsupported/empty/conflicting/unlock outcomes, using strict supported-format decoding with per-item skipped reasons. Valid imported items can apply despite individual skips; no universal whole-document atomicity or all-format round-trip is promised. Direct secret export requires explicit selected connections in addition to the allowance grant. Export material is a projection, not a separately kept document.
