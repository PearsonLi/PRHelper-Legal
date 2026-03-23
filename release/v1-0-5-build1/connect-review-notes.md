---
title: Connect Review Notes - v1.0.5 build 1
permalink: /release/v1-0-5-build1/connect-review-notes/
---

# Review Notes (v1.0.5 build 1)

## EN
Release: v1.0.5 (build 1)
- No login/account is required. Data is local-first by default.
- Main paywall entry paths:
  1. Settings -> Unlock Pro
  2. Trip-limit interception when creating a new trip beyond free capacity
  3. Family-locked flows (member switch/add/edit when Family is not unlocked)
- Redeem path: Paywall -> "Redeem Code" (single redemption entry for Pro/Family product codes).
- Restore path: Paywall -> "Restore Purchases".
- Current purchase model:
  - Free: single member, trip records limited (current free cap in app).
  - Pro Lifetime: unlocks unlimited trip records.
  - Family Lifetime: unlocks family multi-member management (up to 10) and includes Pro capacity.
  - Monthly subscription (while active): unlocks Pro + Family capacity; when expired, locked features are re-locked unless covered by lifetime purchase.
- Migration/recovery notes for this build:
  - Reinstall/cloud restore keeps member-domain records and settings in recovery path.
  - Family lock falls back to primary-member view without deleting stored family data.
- Version-scoped legal URLs:
  - Terms EN: https://pearsonli.github.io/PRHelper-Legal/terms/en/v1-0-5-build1/
  - Privacy EN: https://pearsonli.github.io/PRHelper-Legal/privacy/en/v1-0-5-build1/

## ZH
发布版本：v1.0.5（build 1）
- 应用无需账号登录，数据默认本地优先。
- 主要付费墙入口：
  1. 设置 -> 解锁专业版
  2. 新增旅行记录超过免费容量时自动拦截
  3. 家庭版未解锁时的成员切换/新增/编辑入口
- 优惠码兑换路径：付费墙 -> “使用优惠码兑换”（专业版/家庭版共用一个兑换入口）。
- 恢复购买路径：付费墙 -> “恢复购买”。
- 当前收费模型：
  - 免费版：单成员，旅行记录数量受免费上限约束（以应用当前上限为准）。
  - 专业版买断：解锁无限旅行记录。
  - 家庭版买断：解锁最多 10 位家庭成员管理，并包含专业版容量。
  - 月订阅有效期内：解锁专业版 + 家庭版容量；订阅到期后，如无买断覆盖，将恢复锁定。
- 本版本迁移/恢复说明：
  - 重装/云端恢复路径保留成员域记录与设置。
  - 家庭版未解锁时回退到主成员视图，但不会删除已存储的家庭数据。
- 本版本法务链接：
  - 服务条款（中文）：https://pearsonli.github.io/PRHelper-Legal/terms/zh/v1-0-5-build1/
  - 隐私政策（中文）：https://pearsonli.github.io/PRHelper-Legal/privacy/zh/v1-0-5-build1/
