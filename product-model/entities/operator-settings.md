---
{
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
  "singleton": true
}
---




# Operator settings

Effective Product-wide deployment-principal and direct-export settings.

## Information kept

- **Login name** — the effective deployment operator sign-in name, overridden by saved operator preferences where configured.
- **Deployment credential** — the deployment administrator password/token authority.
- **Token-login availability** — whether browser entry accepts the deployment token sign-in route.
- **Owner claim** — whether the operator identity has been claimed through Owner establishment.
- **Second factor enabled** — whether deployment sign-in requires its configured second-factor response.
- **Secret export allowance** — whether direct HTTP export may disclose selected upstream secrets.
