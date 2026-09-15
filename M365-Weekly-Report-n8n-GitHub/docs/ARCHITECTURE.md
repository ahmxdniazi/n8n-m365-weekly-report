# Architecture

## High-Level Flow

```text
Schedule
   |
   v
Configuration
   |
   +--> Microsoft Graph: Organisation
   |
   +--> Microsoft Graph: Subscribed SKUs
   |
   +--> Microsoft Graph: Users (paginated)
   |
   v
Normalisation
   |
   +--> Licence utilisation
   +--> Domain segmentation
   +--> KPI calculation
   +--> Blocked/unlicensed analysis
   +--> Week-over-week comparison
   |
   v
Consolidated Dataset
   |
   +--> Excel workbook
   +--> CSV exports
   |
   v
SharePoint Archive
   |
   v
HTML Executive Email
   |
   v
Microsoft Graph sendMail
```

## Data Model

The consolidated dataset contains:

- `meta`
- `kpis`
- `licenceRows`
- `userReport`
- `domainSummary`
- `dedicatedDomains`
- `blockedRows`
- `blockedCount`
- `unlicensedRows`
- `unlicensedCount`
- `reclamationCandidates`
- `weekOverWeek`
- `distribution`

The final reporting nodes consume this common dataset rather than independently querying Microsoft Graph.
