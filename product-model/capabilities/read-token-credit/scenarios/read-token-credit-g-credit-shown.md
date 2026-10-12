---
{
  "kind": "primary",
  "routes": {
    "main": "G credit shown"
  },
  "steps": [
    {
      "text": "Present the downstream credential and request credit information.",
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
      "text": "Consult the System token.",
      "kind": "condition",
      "entities": [
        {
          "entity": "system-token",
          "effect": "reads",
          "facts": [
            "Token limit",
            "Tokens used",
            "Money limit",
            "Money used"
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
      "text": "The Token totals and used amounts are returned; group/local profile spendability is not represented as this credit result.",
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









# Read token credit credit shown

## Trigger

Present the downstream credential and request credit information.

## Outcome

The Token totals and used amounts are returned; group/Account spendability is not represented as this credit result.

## Edge cases

- The linked credential branch requires current Team mode, an existing active Account and its current Policy; current model/member grants, owned plan and any allowed request preferences constrain forwarding. System-token admission keeps its separate credential contract. Admission refusal does not perform upstream inference.
