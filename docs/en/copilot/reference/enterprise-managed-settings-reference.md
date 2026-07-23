---
source_path: "/en/copilot/reference/enterprise-managed-settings-reference"
title: "Enterprise managed settings reference"
intro: "Reference for the enterprise managed settings schema used by Copilot clients."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "Reference"
    href: "/en/copilot/reference"
  - title: "Managed settings reference"
    href: "/en/copilot/reference/enterprise-managed-settings-reference"
---

# Enterprise managed settings reference

Reference for the enterprise managed settings schema used by Copilot clients.

Use this reference to understand the currently supported keys in `managed-settings.json`.

For deployment methods, see [Configuring enterprise-managed settings](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/configure-enterprise-managed-settings#choosing-a-deployment-method).

## Precedence rules

When multiple settings sources are present, settings earlier in this list take precedence over settings later in the list:

1. MDM-managed settings
2. Server-managed settings
3. File-based settings
4. User-level settings

## Supported keys

<div class="ghd-tool rowheaders">

| Key                                        | Type     | Accepted values                                                                                                                                                                                                                                | Purpose                                                         |
| ------------------------------------------ | -------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------- |
| `permissions.disableBypassPermissionsMode` | `string` | `"disable"`                                                                                                                                                                                                                                    | Disables bypass or YOLO-style allow-all behavior                |
| `permissions.model`                        | `string` | `"auto"`                                                                                                                                                                                                                                       | Sets auto model selection as the default for new conversations  |
| `enabledPlugins`                           | `object` | Key format: `PLUGIN-NAME@MARKETPLACE-NAME`; value: `true` (enable) or `false` (disable)                                                                                                                                                        | Enables or disables specific plugins by key                     |
| `extraKnownMarketplaces`                   | `object` | Named marketplace objects; supported source types: `"github"`, `"git"`, `"directory"`                                                                                                                                                          | Adds plugin marketplaces that users can access                  |
| `strictKnownMarketplaces`                  | `array`  | Array of marketplace objects; supported source types: `"github"`, `"git"`, `"url"`, `"npm"`, `"file"`, `"directory"`, `"hostPattern"`, `"pathPattern"`                                                                                         | Restricts plugin installation to explicitly listed marketplaces |
| `telemetry`                                | `object` | `enabled` (`boolean`), `endpoint` (`string`), `protocol` (`"http/json"` or `"http/protobuf"`), `captureContent` (`boolean`), `lockCaptureContent` (`boolean`), `serviceName` (`string`), `resourceAttributes` (`object`), `headers` (`object`) | Configures OpenTelemetry export for VS Code                     |

</div>

## Example configuration

The following example shows these keys in one managed settings file.

```json
{
  "permissions": {
    "disableBypassPermissionsMode": "disable",
    "model": "auto"
  },
  "enabledPlugins": {
    "my-plugin@agent-skills": true
  },
  "extraKnownMarketplaces": {
    "agent-skills": {
      "source": {
        "source": "github",
        "repo": "OWNER/REPO"
      }
    }
  },
  "strictKnownMarketplaces": [
    {
      "source": "github",
      "repo": "OWNER/REPO"
    }
  ],
  "telemetry": {
    "enabled": true,
    "endpoint": "https://otel-collector.example.com",
    "protocol": "http/protobuf",
    "captureContent": false,
    "lockCaptureContent": true,
    "serviceName": "copilot",
    "resourceAttributes": {
      "deployment.environment": "production"
    },
    "headers": {
      "Authorization": "Bearer TOKEN"
    }
  }
}
```

## `enabledPlugins`

Defines plugins that are automatically installed or blocked for all enterprise users. Each entry uses the format `PLUGIN-NAME@MARKETPLACE-NAME` as the key, with a boolean value: `true` to require the plugin to be enabled, or `false` to require it to be disabled. See [About enterprise-managed plugin standards](/en/copilot/concepts/agents/about-enterprise-plugin-standards).

## `extraKnownMarketplaces`

Defines additional plugin marketplaces available to users. Each entry is a named marketplace object containing a `source` property. The following source types are supported:

* `"github"` — requires `repo` in `OWNER/REPO` format; optional `ref` (branch, tag, or SHA) and `path` (subdirectory)
* `"git"` — requires `url`; optional `ref` and `path`
* `"directory"` — requires `path`

See [About enterprise-managed plugin standards](/en/copilot/concepts/agents/about-enterprise-plugin-standards).

## `strictKnownMarketplaces`

Restricts plugin installation to only the marketplaces explicitly defined by the enterprise. An empty array means complete lockdown. Each entry is a marketplace object with a `source` property indicating the source type. The following source types are supported:

* `"github"` — requires `repo` in `OWNER/REPO` format; optional `ref` and `path`
* `"git"` — requires `url`; optional `ref` and `path`
* `"url"` — requires `url`; optional `headers` object
* `"npm"` — requires `package`
* `"file"` — requires `path`
* `"directory"` — requires `path`
* `"hostPattern"` — requires `hostPattern` (regex matching marketplace hosts)
* `"pathPattern"` — requires `pathPattern` (regex matching marketplace paths)

## `permissions`

### `disableBypassPermissionsMode`

Prevents users from enabling bypass mode (also known as "YOLO mode") in Copilot CLI and VS Code. Bypass mode lets an agent run commands, access files, and fetch URLs without asking for approval.

When you set `disableBypassPermissionsMode` to `"disable"`, users cannot turn on bypass mode in either client:

* In Copilot CLI, the `--yolo` and `--allow-all` command-line options and the `/yolo` and `/allow-all` slash commands are blocked. Individual flags such as `--allow-all-tools` and `--allow-all-paths` are not blocked.
* In VS Code, the global auto-approve setting (`chat.tools.global.autoApprove`), also known as "YOLO mode," is turned off and cannot be re-enabled.

### `model`

Sets auto model selection as the default for new conversations in Copilot CLI. See [About Copilot auto model selection](/en/copilot/concepts/models/auto-model-selection).

When you set `permissions.model` to `"auto"`, new sessions use Auto model unless the user specifies a different model on a per-conversation basis.

## `telemetry`

Configures OpenTelemetry export, routing Copilot usage data to a collector of your choice.

When you set the `telemetry` property, Copilot telemetry is sent to the endpoint you specify. The following sub-properties are supported:

* `enabled`: Set to `true` to turn on telemetry export, or `false` to turn it off.
* `endpoint`: The URL of your OTLP collector (for example, `https://otel-collector.example.com`).
* `protocol`: The transport protocol for telemetry export. Accepted values are `"http/json"` and `"http/protobuf"`.
* `captureContent`: Set to `true` to include prompt and response content in the telemetry payload, or `false` to exclude it.
* `lockCaptureContent`: Set to `true` to prevent users from changing the `captureContent` setting.
* `serviceName`: A label for the telemetry service name (for example, `"copilot"`).
* `resourceAttributes`: An object of OpenTelemetry resource attributes to attach to all exported telemetry (for example, `{"deployment.environment": "production"}`).
* `headers`: An object of HTTP headers to include with each telemetry request (for example, an `Authorization` header for your collector).
