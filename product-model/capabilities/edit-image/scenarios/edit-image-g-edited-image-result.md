---
{
  "kind": "primary",
  "routes": {
    "main": "G edited image result"
  },
  "steps": [
    {
      "text": "Supply prompt, model, parameters and required reference images.",
      "kind": "actor",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      },
      "actor": "gateway-client"
    },
    {
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      },
      "actor": "gateway-client",
      "text": "For the linked credential branch, consult Account token, Account, Access policy, Team settings using the actual presented credential and fresh linked-account eligibility. The privileged credential branch does not require a linked profile.",
      "kind": "condition",
      "entities": [
        {
          "entity": "account-token",
          "effect": "reads",
          "facts": [
            "Status",
            "Scopes",
            "Model restrictions",
            "Denylist",
            "IP restrictions",
            "Expiry",
            "Token group",
            "Route group",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Account",
            "Routing plan",
            "Neutralization"
          ]
        },
        {
          "entity": "account",
          "effect": "reads",
          "facts": [
            "Status",
            "Policy",
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used",
            "Request preferences"
          ]
        },
        {
          "entity": "access-policy",
          "effect": "reads",
          "facts": [
            "All models",
            "Models",
            "Route members",
            "Request rate",
            "Personal routing",
            "Request preference editing"
          ]
        },
        {
          "entity": "team-settings",
          "effect": "reads",
          "facts": [
            "Operating mode"
          ]
        }
      ]
    },
    {
      "text": "Consult the System token. Consult the Route. Consult the Route member.",
      "kind": "condition",
      "entities": [
        {
          "entity": "system-token",
          "effect": "reads",
          "facts": [
            "Status",
            "Scopes",
            "Model restrictions",
            "IP restrictions",
            "Expiry"
          ]
        },
        {
          "entity": "route",
          "effect": "reads",
          "facts": [
            "Model name/pattern",
            "Status",
            "Routing mode",
            "Single member",
            "Forwarded-name mapping",
            "Routing overrides"
          ]
        },
        {
          "entity": "route-member",
          "effect": "reads",
          "facts": [
            "Route",
            "Connection",
            "Group name",
            "Status",
            "Priority",
            "Weight",
            "Forwarded-name mapping",
            "Price layer",
            "Health",
            "Cooldown",
            "Manual intent",
            "Automatic origin"
          ]
        }
      ],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      },
      "actor": "gateway-client"
    },
    {
      "text": "Return the upstream image response without creating local browser history; book only qualifying recognized usage.",
      "kind": "product",
      "entities": [],
      "contexts": {
        "main": {
          "place": "inference-api"
        }
      },
      "actor": "gateway-client"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/relay.go#forwardPassthrough"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/auth/auth.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/store/team_access.go"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/proxy/proxy_health.go"
    }
  ]
}
---









# Edit image edited image result

## Trigger

Supply prompt, model, parameters and required reference images.

## Outcome

The upstream image response is returned without creating browser history; qualifying recognized usage is booked.

## Edge cases

- The direct gateway contract validates the selector and body shape; it passes image/reference requirements through to the selected upstream rather than importing the browser form’s reference-image guard.

- Reject malformed JSON, malformed or duplicate multipart model selectors, a missing model, or a body above the effective configured image ceiling before forwarding. Upstream image failure is returned without automatic replay; the API does not save browser image history or synthesize missing token usage from file count or bytes.

- The linked credential branch requires current Team mode, an existing active Account and its current Policy; current model/member grants, owned plan and any allowed request preferences constrain forwarding. System-token admission keeps its separate credential contract. Admission refusal does not perform upstream inference.
