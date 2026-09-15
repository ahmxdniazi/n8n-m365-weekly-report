# Configuration Guide

All environment-specific reporting configuration is centralised in the `Config` Code node.

## Required

| Setting | Description |
|---|---|
| `organisationName` | Fallback/display name for the tenant |
| `reportOwner` | Team responsible for the report |
| `senderMailbox` | Microsoft 365 mailbox used by Graph `sendMail` |
| `recipientEmails` | Report recipients |
| `sharePointSiteId` | Target SharePoint site ID |
| `sharePointFolderPath` | Archive folder path |

## Reporting Rules

| Setting | Description |
|---|---|
| `domainDisplayNames` | Friendly names for dedicated domain worksheets |
| `alwaysIncludeDomains` | Domains that should always receive dedicated worksheets |
| `minUsersForOwnTab` | Minimum number of accounts for automatic domain worksheet creation |
| `excludeOnMicrosoftDomain` | Whether `.onmicrosoft.com` domains are excluded from dedicated worksheets |
| `highUsagePct` | Critical licence utilisation threshold |
| `mediumUsagePct` | Watch threshold |
| `weekEndingDayOfWeek` | Week-ending anchor used by reporting-period logic |
| `excludedSkus` | Licence SKUs excluded from utilisation reporting |
| `skuFriendlyNames` | Friendly display names for SKU part numbers |

## Safety

Keep:

```javascript
skipEmailSend: true
```

while testing.

Only change it to `false` after validating data collection, workbook generation, SharePoint uploads, and email payload generation.

## Credentials

Authentication is configured through the n8n credential attached to the Microsoft Graph HTTP Request nodes.

Do not place:

- Client secrets
- Access tokens
- Certificates
- Private keys
- Passwords

inside the `Config` node or Git repository.
