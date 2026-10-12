---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "change-webdav-settings"
    },
    {
      "type": "capability",
      "id": "test-webdav"
    },
    {
      "type": "capability",
      "id": "download-webdav"
    },
    {
      "type": "capability",
      "id": "upload-webdav"
    },
    {
      "type": "entity",
      "id": "webdav-settings"
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



# Independent WebDAV directions share one execution slot and preserve skipped results

Download and upload have independent remote connections, protected credentials, enablement and schedules. Test/download/upload share one active-run slot. Download unlocks and imports supported material; upload preserves protected remote AAH/unknown formats and writes its canonical representation. Service upload includes secrets and bypasses the direct HTTP export allowance. Disabled directions can remember skipped results without gaining credential/schedule editing. Setup test/download first saves download settings, enables download, disables upload and leaves schedules off.
