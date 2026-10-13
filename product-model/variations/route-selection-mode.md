---
{
  "kind": "configuration",
  "of": "business-rule",
  "settings": [
    {
      "entity": "route",
      "fact": "Routing mode"
    }
  ],
  "takesEffect": "Each time a request, or a selection explanation, picks a member of the Route. A mode change applies to later picks.",
  "stability": "Nothing is captured per request or session. Affinity can keep a bound channel across a mode change while that channel stays eligible.",
  "alternatives": [
    {
      "id": "auto-mode-follows-deployment-scoring-settings",
      "selectedWhen": "Routing mode is Auto. A missing mode uses Auto, and so does Single without a current pinned member."
    },
    {
      "id": "weighted-mode-uses-member-weights-only",
      "selectedWhen": "Routing mode is Weighted."
    },
    {
      "id": "latency-mode-scores-by-observed-latency",
      "selectedWhen": "Routing mode is Latency."
    },
    {
      "id": "adaptive-mode-scores-by-latency-and-failures",
      "selectedWhen": "Routing mode is Adaptive."
    },
    {
      "id": "single-route-pin",
      "selectedWhen": "Routing mode is Single and the Single member is still a member of the Route."
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/domain/models.go#NormalizeRoutingMode"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/httpapi/admin_validation.go#validRoutingMode"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/scoring.go#pick"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "internal/routing/routing.go#evaluate"
    }
  ]
}
---

# Route selection mode

Each Route chooses ahead of time how a member is picked from its highest eligible priority tier: by the deployment's own scoring settings, by weight alone, by latency, by latency and failures, or pinned to one member. All five policies are supported side by side.
