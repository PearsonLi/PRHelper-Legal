# Data Schema History

## Rule (Release Blocking)
- Any change touching persisted DB/data structure must:
  - bump `CURRENT_DATA_SCHEMA_VERSION` in `/Users/pearsonli/ImmigrationTracker/src/core/dataSchema.ts`
  - append one new entry to `DATA_SCHEMA_HISTORY`
  - update this document with the new structure notes

## Version Log

### v3 (Current)
- Introduced in app version: `1.0.5`
- Released at: `2026-03-22`
- Persisted structures:
  - `LocationEvent.isDeparture` (0|1): marks the start boundary of a trip
  - `LocationEvent.isEntry` (0|1): marks the end boundary of a trip
  - `BackupTravelRecord.isDeparture` / `BackupTravelRecord.isEntry` (optional)
- Migration notes:
  - Existing events backfilled from OUTSIDE_CA range boundaries and note markers.
  - No calculation logic changes. Fields are purely metadata for display and merge prevention.

### v2
- Introduced in app version: `1.0.3`
- Released at: `2026-03-16`
- Persisted structures:
  - Persisted state: `members[]`, `currentMemberId`, `memberSettings{}` (per-member PR settings)
  - `LocationEvent.memberId` (defaulted to `primary-member` on migration)
  - Cloud backup payload adds `backup.members[]`, `backup.currentMemberId`, `backup.memberSettings[]`
  - `backup.settings.familyLicensePurchased` for Family entitlement
- Migration notes:
  - v1 global PR settings + manual prior days moved into `memberSettings.primary-member`.
  - Legacy events/pre-PR records without `memberId` are assigned to `primary-member`.

### v1
- Introduced in app version: `1.0.0`
- Released at: `2026-03-01`
- Persisted structures:
  - Cloud backup payload root: `{ schemaVersion, exportedAt, backup, appPreferences }`
  - `backup.records[]`: travel records (`departureDate`, `arrivalDate`, `status`, `type`, `source`, `isConfirmed`, `memberId`)
  - `backup.settings`: PR dates, reminder settings, license/consent flags
  - `backup.prePrRecords[]`: temporary residence records (`type`, `fromDate`, `toDate`)
  - `backup.updatedAtMs`: domain timestamps (`records/settings/prePrRecords/appPreferences`)
  - `appPreferences`: language, travel input mode, theme
- Migration notes:
  - Baseline schema.
  - Unknown future schema versions are ignored by current app to prevent unsafe data overwrite.
