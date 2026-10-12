---
{
  "scope": "Established core console, documented management subset, inference, access, routing, accounting, operational records, native check-ins, exchange, runtime and restoration code.",
  "method": "Static tracing from entry and console actions through handlers, persistence, authorization and observable results.",
  "covered": [
    {
      "description": "Entry and team access handlers with console session and role branches.",
      "paths": [
        "web/src/App.tsx",
        "web/src/session.tsx",
        "web/src/team/",
        "internal/httpapi/session.go",
        "internal/httpapi/team.go",
        "internal/httpapi/team_auth.go",
        "internal/httpapi/team_admin.go",
        "internal/httpapi/team_members.go",
        "internal/httpapi/team_codes.go",
        "internal/httpapi/team_oauth.go",
        "internal/httpapi/team_oauth_admin.go",
        "internal/httpapi/team_preferences.go"
      ]
    },
    {
      "description": "Connection, credential and observed-model console flows and administration services.",
      "paths": [
        "web/src/features/Channels.tsx",
        "web/src/features/ChannelModels.tsx",
        "web/src/features/channels/",
        "internal/httpapi/admin_connections.go",
        "internal/httpapi/admin_channels.go",
        "internal/httpapi/admin_credentials.go",
        "internal/httpapi/discovery.go",
        "internal/account/",
        "internal/discovery/",
        "internal/store/discovery.go"
      ]
    },
    {
      "description": "Route, member, alias, unification and selected catalog implementation.",
      "paths": [
        "web/src/features/Models.tsx",
        "web/src/features/models/",
        "internal/httpapi/admin_routes.go",
        "internal/httpapi/admin_ops.go",
        "internal/httpapi/model_alias.go",
        "internal/httpapi/admin_unify.go",
        "internal/httpapi/admin_model_bootstrap.go",
        "internal/httpapi/admin_model_catalog.go",
        "internal/store/route.go",
        "internal/store/model_alias.go",
        "internal/store/unify.go",
        "internal/routing/",
        "internal/modelcatalog/service.go",
        "internal/domain/capability.go",
        "internal/store/model_capabilities.go",
        "internal/store/model_metadata.go"
      ]
    },
    {
      "description": "Downstream Tokens, group budgets, member arrangements and recorded billing implementation.",
      "paths": [
        "web/src/features/Keys.tsx",
        "web/src/features/MemberModelsPage.tsx",
        "web/src/member/RouteOrderDialog.tsx",
        "internal/httpapi/admin_keys.go",
        "internal/httpapi/admin_usage.go",
        "internal/httpapi/team_resources.go",
        "internal/httpapi/team_usage.go",
        "internal/httpapi/relay.go",
        "internal/auth/",
        "internal/store/downstream_key.go",
        "internal/store/team_access.go",
        "internal/store/group.go",
        "internal/store/usage.go",
        "internal/proxy/proxy_health.go",
        "internal/proxy/proxy_keypool.go",
        "internal/usage/",
        "internal/domain/team.go",
        "web/src/member/MemberKeysSource.ts"
      ]
    },
    {
      "description": "Diagnostic and personal workbench execution and browser-origin persistence.",
      "paths": [
        "web/src/features/workbench/",
        "web/src/lib/consoleStore.ts",
        "internal/httpapi/try.go"
      ]
    },
    {
      "description": "Request, audit and in-memory live-record presentation and handlers.",
      "paths": [
        "web/src/features/Logs.tsx",
        "web/src/features/LiveTracePanel.tsx",
        "web/src/features/ops/AuditPanel.tsx",
        "internal/httpapi/operations.go",
        "internal/httpapi/audit.go",
        "internal/httpapi/livetrace_handler.go",
        "internal/store/proxylog.go",
        "internal/livetrace/"
      ]
    },
    {
      "description": "Native check-in handlers, adapters and visible history.",
      "paths": [
        "web/src/features/Checkins.tsx",
        "web/src/features/ops/CheckinsPanel.tsx",
        "internal/httpapi/checkin.go",
        "internal/checkin/"
      ]
    },
    {
      "description": "Connection exchange, WebDAV and carried first-access orchestration.",
      "paths": [
        "web/src/features/Exchange.tsx",
        "web/src/features/SetupWizard.tsx",
        "internal/httpapi/exchange.go",
        "internal/httpapi/webdav.go",
        "internal/exchange/",
        "internal/webdavsync/"
      ]
    },
    {
      "description": "Runtime override application and monetary display settings.",
      "paths": [
        "web/src/features/ops/RuntimeSettingsPanel.tsx",
        "web/src/features/AppearancePanel.tsx",
        "internal/httpapi/runtime_settings.go",
        "internal/httpapi/display_settings.go",
        "internal/runtimeconfig/",
        "internal/store/display_settings.go"
      ]
    },
    {
      "description": "Online snapshot inventory/creation and offline replacement implementation.",
      "paths": [
        "web/src/features/ops/BackupsPanel.tsx",
        "internal/httpapi/backup.go",
        "internal/backup/",
        "cmd/server/main.go"
      ]
    },
    {
      "description": "Registered entry, management subset and documented inbound contracts.",
      "paths": [
        "internal/httpapi/router.go",
        "docs/reference/admin-api.md",
        "docs/clients/",
        "docs/billing/",
        "docs/operations/backup-restore.md",
        "docs/operations/webdav-sync.md"
      ]
    }
  ],
  "unmapped": [
    {
      "description": "Remaining management, legacy redemption and bulk/export handlers.",
      "paths": [
        "internal/httpapi/"
      ]
    },
    {
      "description": "Personal plan replacement, rename and deletion handlers and HTTP-only personal Token plan selection beyond the inspected console controls.",
      "paths": [
        "internal/httpapi/team_resources.go"
      ]
    },
    {
      "description": "Operator identity, owner claim and second-factor administration surfaces.",
      "paths": [
        "web/src/features/OperatorProfilePanel.tsx",
        "web/src/features/ops/TOTPPanel.tsx",
        "internal/httpapi/"
      ]
    },
    {
      "description": "Remaining model-capability registry and catalog administration.",
      "paths": [
        "internal/httpapi/admin_model_capabilities.go",
        "internal/modelcatalog/"
      ]
    },
    {
      "description": "Upstream financial sweep and reconciliation implementation.",
      "paths": [
        "internal/financesweep/"
      ]
    },
    {
      "description": "Managed probe, public-status probe, health sweep and recovery settings.",
      "paths": [
        "internal/probe/",
        "internal/siteprobe/",
        "internal/healthsweep/"
      ]
    },
    {
      "description": "Remaining provider profiles and transformations, audio, moderation and complete protocol adaptation.",
      "paths": [
        "internal/adapters/",
        "internal/proxy/"
      ]
    },
    {
      "description": "Alert, news and outbound delivery implementation.",
      "paths": [
        "internal/alerts/",
        "internal/webhook/",
        "internal/sitenews/"
      ]
    },
    {
      "description": "Plugin marketplace/process management and update implementation.",
      "paths": [
        "internal/plugins/",
        "internal/selfupdate/",
        "internal/updatecheck/"
      ]
    },
    {
      "description": "Additional maintenance, destructive retention and external custom check-in implementation.",
      "paths": [
        "internal/maintenance/",
        "web/src/features/ops/ExternalCheckinsPanel.tsx",
        "web/src/features/ops/MaintenancePanel.tsx"
      ]
    },
    {
      "description": "Metrics, health, readiness and remaining operational recovery endpoints.",
      "paths": [
        "internal/observability/",
        "internal/httpapi/"
      ]
    }
  ],
  "exclusions": [
    {
      "description": "Generated embedded bundles and rendering/style support.",
      "paths": [
        "internal/webui/dist/",
        "web/src/components/"
      ]
    },
    {
      "description": "E2E harness, CI and release orchestration.",
      "paths": [
        "cmd/e2e-runner/",
        "cmd/e2e-mock/",
        ".github/"
      ]
    },
    {
      "description": "Documentation generators and build tooling.",
      "paths": [
        "tools/docsgen/",
        "docs/.vitepress/"
      ]
    }
  ],
  "limitations": [
    {
      "description": "Configured external Account, identity, check-in and WebDAV response handling whose remote success depends on systems outside these source paths.",
      "paths": [
        "internal/account/",
        "internal/httpapi/team_oauth.go",
        "internal/checkin/",
        "internal/webdavsync/"
      ]
    },
    {
      "description": "Snapshot validation and cryptographic reopening across deployment key-material changes.",
      "paths": [
        "internal/backup/service.go",
        "internal/crypto/"
      ]
    },
    {
      "description": "Upstream error payload propagation whose arbitrary contents cannot establish universal credential-free output.",
      "paths": [
        "internal/proxy/",
        "internal/httpapi/relay.go"
      ]
    }
  ]
}
---




# Coverage


