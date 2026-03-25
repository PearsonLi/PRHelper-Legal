---
title: Release Notes - v1.0.5 build 6
permalink: /release/v1-0-5-build6/release-notes/
---

# Release Notes - v1.0.5 (build 6)

- Generated at: 20260324_1646
- Previous version baseline: v1.0.5-build5

## 1) App Store Metadata (English)

### App Name
CanResidency

### Subtitle
Track PR and citizenship days accurately

### Promotional Text
Local-first travel tracking for Canada PR and citizenship calculations, with rolling 5-year forecasts and risk reminders.

### Description
CanResidency helps permanent residents maintain accurate residency records with strict day-level counting aligned to official IRCC rules.

Key capabilities:
- Log departure/return records with day-level validation.
- Compute PR obligation (730 days) and citizenship progress (1095 days).
- Manage temporary-residence records in Travel history for citizenship pre-PR credit.
- Forecast trend with rolling 5-year windows and risk reminders.
- Export and import travel records for backup and audit.

All data stays on device by default. This app is a tracking and planning tool, not legal advice.

Terms of Use: https://pearsonli.github.io/PRHelper-Legal/terms/en/v1-0-5-build6/
Privacy Policy: https://pearsonli.github.io/PRHelper-Legal/privacy/en/v1-0-5-build6/

### Keywords
Canada PR,residency,citizenship,travel history,IRCC,physical presence,immigration tracker

### What’s New
- See section "Version Delta" below.

### Review Notes (English)
- No login required.
- No in-app account creation/login system; purchases are tied to Apple ID entitlements only.
- Core features run locally without server account.
- Pro access unlocks PR/Citizenship advanced pages and travel import/export.
- In-app purchase uses Apple/RevenueCat configuration.
- Test path:
  1. Launch app.
  2. Open Travel and create a trip.
  3. Open Settings -> Unlock Pro -> verify paywall appears.
  4. After Pro entitlement is active, verify PR/Citizenship pages and Travel Import/Export are accessible.

## 2) App Store Metadata (中文)

### App 名称
CanResidency

### 副标题
精准记录永居与入籍居住天数

### 推广文本
纯本地记录出入境，按官方 5 年滚动规则计算永居/入籍天数，支持趋势预测与风险提醒。

### 应用描述
CanResidency用于帮助加拿大永久居民记录旅行与居住天数，按天粒度执行官方口径计算。

核心能力：
- 记录离开加拿大 / 返回加拿大日期并执行重叠校验。
- 计算永居义务（730 天）和入籍进度（1095 天）。
- 在旅行历史中管理“临时居留”并用于入籍折算。
- 提供 5 年滚动趋势图与风险提醒。
- 提供旅行记录导入导出能力，便于备份与校核。

数据默认仅存储在本机。本应用为记录与规划工具，不构成法律意见。

服务条款：https://pearsonli.github.io/PRHelper-Legal/terms/zh/v1-0-5-build6/
隐私政策：https://pearsonli.github.io/PRHelper-Legal/privacy/zh/v1-0-5-build6/

### 关键词
永居,入籍,出入境,旅行记录,居住天数,加拿大移民,IRCC

### 本版本更新
- 见下方「版本差异」章节。

### 审核备注（中文）
- 应用无需登录账号。
- 应用不提供自建账号注册/登录，专业版购买仅依赖 Apple ID 下的内购权益。
- 核心记录与计算均可在本地完成。
- 专业版解锁永居/入籍高级页面及旅行记录导入导出。
- 内购通过 Apple / RevenueCat 配置。
- 审核建议路径：
  1. 启动应用；
  2. 在旅行页新增记录；
  3. 设置页点击“立即解锁专业版”，确认付费墙可见；
  4. 激活专业版后，确认永居/入籍页面与导入导出页面可访问。

## 3) Version Delta (vs previous)

- f97f566 fix: resolve all 31 typecheck errors from LocationEvent removal
- 1aaf388 refactor: remove LocationEvent from runtime — direct Trip→DayPresence path
- 879abe7 refactor: remove destination field from TripRecord — use countryCode only
- 921b3e9 fix: add missing imports and remove zombie import causing crash
- bfbe693 refactor: delete ~900 lines of legacy event-manipulation dead code
- dfba8e7 refactor: remove events from user-interaction paths (violations #2 #3 #5)
- fb1fe10 refactor: enforce events-only-for-calculation principle (3 violations fixed)
- 4809356 refactor: remove auto-tracking code (never released)
- 9a4f753 fix: Overview country display reads from Trip table, not events
- 9dd383c feat(ux): add haptic feedback to Dashboard profile switcher
- a8b91cb fix: trip destination display + typecheck zero errors
- 1c40828 fix: 4 type-system bugs — critical DayPresence mismatch + category + MigratableState + CloudSync
- 2736479 fix(travel): show country name in timeline when destination text is empty
- 0163d13 feat(travel): show inline "数据计算中..." indicator during trip save/delete
- 61737be feat(pre-pr): inline warning for records outside valid pre-PR period
- 94b987e fix(citizenship): show half-day precision for pre-PR credit (660.5 not 661)
- 7e9d8fd perf(render): fix cascade re-render from handleSelectMember 18-dep bloat
- 8242ab8 fix(migration): restore trips from legacy v1.0.2/v1.0.3/v1.0.4 cloud snapshots
- d337b08 fix(cloud): restore trips on reinstall — check backup.trips not just backup.records
- e8a8227 perf(trip-save): lightweight refresh after save, skip full refreshData
- cc14202 perf(startup): background prewarm all family members' cache after init
- 7b92d2b perf(member-switch): per-member data cache for instant switching
- e557b22 test+fix: add 11 HIGH-risk release gate tests, fix 2 bugs found
- 6ead833 refactor(db): simplify normalizeState — remove ~100 lines of dead code
- c00938b refactor: replace locationTracker with stubs, remove insertLocationEvent
- 5790e4e refactor: stub auto-tracking functions and simplify presenceAdapter
- d06a283 refactor: remove note marker system (ZERO_ABSENCE_TRIP / OPEN_DEPARTURE)
- 8f24a21 refactor(ui): remove isZeroAbsenceTrip field from CalendarTimelineRange
- 88a5722 fix(travel): show correct arrival date when editing zero-absence trips
- bf87f4e chore(db): remove backupRecordsToManualEvents and legacy fallback path
- 0e7b235 chore(db): remove dead code — eventsToBackupRecords and normalizePrePrRecordsForReplace
- 0bceda0 refactor(db): merge PrePrRecord into Trip table (category='pre-pr-residence')
- 8209942 perf(db): stop persisting events — derive from trips on load
- 3585c9b refactor(core): wire DayPresenceRecord through entire calculation pipeline
- eaac638 refactor(core): introduce DayPresenceRecord as lightweight calculation input
- 276c71b perf(core): replace Intl.DateTimeFormat with pure math in getNextLocalDayStartMs
- ce44ff6 perf(db): skipNormalize for all pure-settings mutators + parallelize member switch
- 4ab33ee perf(db): async CloudKit push + skip normalizeState for Trip CRUD
- 9e7737b chore: checkpoint latest commercial changes
- c2950d4 fix(cloud): stop trip duplication on every cloud sync cycle
- 4b4f292 refactor(trip): store dates as strings, remove dep/arr IN_CA events
- 10c7812 feat(import): JSON import creates Trip records via upsertTrip
- b5d5292 fix(display): skip date offset for trip-based timeline ranges
- 55885b6 perf(db): remove trip→event regeneration from normalizeState hot path
- 8921ca0 feat(trip): complete trip table integration (Steps 8-9)
- 9c828a5 feat(timeline): wire trip-based timeline display into travel tab (Step 7)
- 22b0ff3 feat(timeline): add buildTimelineFromTrips for trip-based display (Step 7)
- 520c7ac feat(travel): switch save/edit/delete to Trip CRUD (Step 6)
- 98874f1 feat(backup): export/import trips in cloud snapshots (v4 payload)
- 38d8575 feat(schema): introduce Trip table as source of truth for travel records (v4)
- cdb7f37 fix(ux): constrain date pickers so return date cannot precede departure
- 36ab7aa fix(import): add isDeparture/isEntry to buildTravelImportPlan upserts

## 4) QA Test Guide

### Required functional checks
1. Onboarding: consent gate and links.
2. Travel: add/update/delete with overlap validation.
3. PR page: chart rendering, threshold crossing, risk reminders.
4. Citizenship page: progress/trend with pre-PR credit reflected from Travel -> Temporary Residence records.
5. Settings: language switch, paywall open, legal pages.
6. Import/Export: JSON backup and PDF generation.
7. Paywall: monthly + one-time actions, restore purchase, links.

### Required regression checks
1. Unit + functional + performance:
```bash
npm run test:all
```
2. Release parity matrix:
```bash
npm run test:official-parity50
```
3. Release gate:
```bash
npm run test:release:full
```

### RevenueCat manual entitlement checks (required)
1. Confirm offering "commercial version" sells:
   - com.pearsonli.PRHelper.pro.monthly.sub_v2
   - com.pearsonli.PRHelper.lifetime_v2
   - com.pearsonli.PRHelper.family_lifetime_v1
2. Confirm entitlement "Canada Residency Pro Pro" includes:
   - com.pearsonli.PRHelper.pro.monthly.sub
   - com.pearsonli.PRHelper.pro.monthly.sub_v2
   - com.pearsonli.PRHelper.lifetime_v2
3. Confirm entitlement "CanResidency Family" includes:
   - com.pearsonli.PRHelper.pro.monthly.sub
   - com.pearsonli.PRHelper.pro.monthly.sub_v2
   - com.pearsonli.PRHelper.family_lifetime_v1

### Screenshot package location
- ./screenshots/en + ./screenshots/zh
- English and Chinese, each includes 7 required pages:
  1. Dashboard
  2. Travel Input
  3. Travel
  4. PR
  5. PR Evaluation Date
  6. Citizenship
  7. Family & PR Settings

### Screenshot generation constraints (locked in release flow)
- Clear existing system/app test data before capture.
- Import fixed release sample dataset (PR settings + trip records + app preferences) before each capture.
- Pro entitlement switch is force-enabled before capture.
- English screenshots are captured with app language = en.
- Chinese screenshots are captured with app language = zh.
- Capture fails if any required page is missing.
