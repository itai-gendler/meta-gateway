---
{
  "kind": "primary",
  "routes": {
    "main": "G response received"
  },
  "steps": [
    {
      "text": "Submit a Responses request with the downstream credential.",
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
      "text": "Consult the System token. Consult the Route. Consult the Route member. Consult the Connection. Consult the Model metadata. Consult the Billing multiplier.",
      "kind": "condition",
      "entities": [
        {
          "entity": "system-token",
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
            "Money used"
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
        },
        {
          "entity": "connection",
          "effect": "reads",
          "facts": [
            "Status",
            "Protocol",
            "Credential association",
            "Routing controls",
            "Forwarding settings"
          ]
        },
        {
          "entity": "model-metadata",
          "effect": "reads",
          "facts": [
            "Model name",
            "Price layer"
          ]
        },
        {
          "entity": "billing-multiplier",
          "effect": "reads",
          "facts": [
            "Model name",
            "Multiplier"
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
      "text": "The response is returned; non-safe failures are not replayed.",
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









# Call responses response received

## Trigger

Submit a Responses request with the downstream credential.

## Outcome

The response is returned; non-safe failures are not replayed.

## Edge cases

- The linked credential branch requires current Team mode, an existing active Account and its current Policy; current model/member grants, owned plan and any allowed request preferences constrain forwarding. System-token admission keeps its separate credential contract. Admission refusal does not perform upstream inference.
