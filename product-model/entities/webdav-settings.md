---
{
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
  ],
  "singleton": true
}
---



# WebDAV settings

The Product-wide independent remote download and upload configuration and last outcomes.

## Information kept

- **Download connection** — the separately configured remote source and credentials for download.
- **Upload connection** — the separately configured remote destination and credentials for upload.
- **Credential availability** — whether each direction has a stored WebDAV login password and backup unlock/encryption password, without disclosing them.
- **Direction enablement** — the independent download/upload enabled choices.
- **Schedules** — the independent direction schedule choices.
- **Last result** — the last success, failure or skipped direction outcome.
