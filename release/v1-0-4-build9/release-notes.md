---
title: Release Notes - v1.0.4 build 9
permalink: /release/v1-0-4-build9/release-notes/
---

# Release Notes - v1.0.4 (build 9)

- Generated at: 20260321_2118
- Previous version baseline: v1.0.4-build8

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
- Support temporary-residence credit in citizenship flow.
- Forecast trend with rolling 5-year windows and risk reminders.
- Export and import travel records for backup and audit.

All data stays on device by default. This app is a tracking and planning tool, not legal advice.

Terms of Use: https://pearsonli.github.io/PRHelper-Legal/terms/en/v1-0-4-build9/
Privacy Policy: https://pearsonli.github.io/PRHelper-Legal/privacy/en/v1-0-4-build9/

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
- 入籍支持临时居留折算模块。
- 提供 5 年滚动趋势图与风险提醒。
- 提供旅行记录导入导出能力，便于备份与校核。

数据默认仅存储在本机。本应用为记录与规划工具，不构成法律意见。

服务条款：https://pearsonli.github.io/PRHelper-Legal/terms/zh/v1-0-4-build9/
隐私政策：https://pearsonli.github.io/PRHelper-Legal/privacy/zh/v1-0-4-build9/

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

- f687cb0 refactor(db): extract schema migration into independent chain-based module
- 73095b2 feat(overview): replace family progress card with inline family overview switch
- c613ef5 fix(bug): preserve family members on reinstall/cloud restore
- ca3930a fix(bug): close trip limit bypass and enforce family primary lock
- 535b335 docs(release): refresh v1.0.4 build 8 Connect copy

## 4) QA Test Guide

### Required functional checks
1. Onboarding: consent gate and links.
2. Travel: add/update/delete with overlap validation.
3. PR page: chart rendering, threshold crossing, risk reminders.
4. Citizenship page: temporary residence tab and credit logic.
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
