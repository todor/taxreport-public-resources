# taxreport.bg — Public Resources

Public configuration files and legal documents for taxreport.bg products.

This repository hosts resources that must be publicly accessible without exposing the private application source code.

## Products

### Chrome Extension

Resources for the taxreport.bg browser extension, which assists users with completing tax declarations in the Bulgarian National Revenue Agency (NRA) portal.

| File | Description |
|---|---|
| [policy.json](chrome-extension/policy.json) | Remote release and access policy |
| [license.en.md](chrome-extension/license.en.md) | Software license — English |
| [license.bg.md](chrome-extension/license.bg.md) | Software license — Bulgarian |
| [privacy.en.md](chrome-extension/privacy.en.md) | Privacy policy — English |
| [privacy.bg.md](chrome-extension/privacy.bg.md) | Privacy policy — Bulgarian |

#### Remote release policy

The extension periodically retrieves its remote policy to determine whether it can connect to the NRA portal.

**Policy URL:**

https://raw.githubusercontent.com/todor/taxreport-public-resources/main/chrome-extension/policy.json

The policy contains the following fields:

| Field | Description |
|---|---|
| `minimum_supported_version` | Minimum extension version allowed to connect |
| `legacy_free_access_enabled` | Whether extension versions without entitlement support may connect |
| `automation_enabled` | Emergency switch to disable new connections |

The extension normally checks the policy every 24 hours and can use its last verified policy for up to 72 hours if retrieval temporarily fails.

Changes take effect on subsequent connections after the updated policy has been retrieved. Existing connections are not interrupted.

#### Updating the release policy

1. Edit `chrome-extension/policy.json` on the `main` branch.
2. Commit the changes.
3. Verify the published JSON at the policy URL above.

**Important:** Release-policy changes can affect whether installed extensions are permitted to operate. Review changes carefully before committing.

## Legal documents

The English and Bulgarian versions of the license and privacy policy are maintained together.

Changes to legal documents should be reviewed and synchronized with their corresponding versions in the private product repository.

## Repository scope

This repository contains publicly accessible configuration and legal documents. It does not contain the application source code.

Access to this repository does not grant permission to use, modify, or redistribute proprietary taxreport.bg software beyond the rights expressly granted by its applicable license.

Additional product resources may be added in separate directories as needed.