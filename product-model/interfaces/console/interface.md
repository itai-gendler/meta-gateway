---
{
  "type": "web",
  "actors": [
    "deployment-administrator",
    "owner",
    "administrator",
    "member"
  ],
  "languages": [
    "en",
    "zh-CN"
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/App.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "web/src/session.tsx"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/session.go#login"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team_oauth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/team.go"
    }
  ],
  "entryPoints": [
    {
      "web": "/console"
    },
    {
      "web": "/app"
    }
  ]
}
---



# Console

The browser contract for entry, gateway administration and personal Account use.
