---
{
  "kind": "primary",
  "routes": {
    "main": "R disconnected"
  },
  "steps": [
    {
      "text": "End the current browser session.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration"
        }
      },
      "actor": "owner"
    },
    {
      "text": "If the Cookie-session logout succeeds, remove the current browser session from server persistence.",
      "kind": "product",
      "actor": "owner",
      "entities": [
        {
          "entity": "account-session",
          "effect": "removes"
        }
      ],
      "contexts": {
        "main": {
          "place": "console::administration"
        }
      }
    },
    {
      "text": "The browser clears credentials and navigation metadata immediately and leaves the workspace; local text and image history remains. Successful cookie logout removes the current server session. A rejected or failed logout leaves local sign-out complete. Signed operator authority is only forgotten locally.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "console::administration"
        }
      },
      "actor": "owner"
    }
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
  ]
}
---









# Sign out disconnected

## Trigger

End the current browser session.

## Outcome

The browser clears credentials and navigation metadata immediately and leaves the workspace; local conversation and image history remains. Successful cookie logout removes the current server session. A rejected or failed logout leaves local sign-out complete. Signed operator authority is only forgotten locally.

## Decision points

### Current authentication and logout outcome

Which credential branch and logout outcome applies? Every branch ends with the browser disconnected.

- Account cookie with successful logout → remove the current server session and clear browser authority.
- Account cookie with failed logout → clear browser authority; do not claim server revocation.
- Signed operator credential → clear its browser copy without a server logout or global revocation.
