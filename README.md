# taxreport.bg — Release Policy

Remote release policy for the taxreport.bg Chrome extension.

The extension periodically retrieves `policy.json` to determine whether it can connect to the Bulgarian National Revenue Agency (NRA) portal.

## Policy

```json
{
  "minimum_supported_version": "1.0.0",
  "legacy_free_access_enabled": true,
  "automation_enabled": true
}
```

| Field | Description |
|---|---|
| `minimum_supported_version` | Minimum extension version allowed to connect. |
| `legacy_free_access_enabled` | Whether free-only extension versions may connect. |
| `automation_enabled` | Emergency switch to disable new connections. |

## Updating the policy

1. Edit `policy.json` on the `main` branch.
2. Change the relevant field.
3. Commit the changes.
4. Verify the published file at:

   `https://raw.githubusercontent.com/<OWNER>/taxreport-release-policy/main/policy.json`

The extension normally refreshes the policy every 24 hours and tolerates temporary retrieval failures for up to 72 hours using its last verified policy.

Changes affect new connections after the extension retrieves the updated policy. Existing connections are not interrupted.

## Licensing

This repository contains release configuration, not the extension source code. Access to this repository does not grant a license to use, modify or redistribute the taxreport.bg extension.

The extension's licensing terms are maintained separately.
