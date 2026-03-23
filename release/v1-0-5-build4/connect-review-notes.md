---
title: Connect Review Notes - v1.0.5 build 4
permalink: /release/v1-0-5-build4/connect-review-notes/
---

# Review Notes (v1.0.5 build 4)

## EN
Release: v1.0.5 (build 4)
- No login/account is required; core tracking/calculation runs locally first.
- Main paywall entry paths:
  1. Settings -> Unlock Pro
  2. Free-limit interception when creating/updating records beyond free capacity
  3. Family-locked member-switch/member-add/member-edit paths
- Purchase/restore/redeem paths:
  - Subscribe / Buy in paywall cards
  - Restore Purchases (paywall footer)
  - Redeem Code (paywall footer)
- Current entitlement model:
  - Authorization is entitlement-driven in app runtime (not product-id hardcoded for unlock decisions).
  - Monthly subscription (active): unlocks Pro + Family capabilities.
  - Legacy monthly and monthly_v2 are both recognized under the same Pro entitlement, so existing subscribers keep access after upgrade.
  - Monthly expired: Pro + Family lock again unless covered by lifetime purchase.
  - Pro Lifetime: unlocks Pro capabilities.
  - Family Lifetime: unlocks Family + Pro capabilities.
- Current free-limit model:
  - Free tier allows up to 5 total records per member (Trip + Temporary Residence combined).
- Temporary Residence entry path in this build:
  - Travel -> History -> Temporary Residence (collapsible card)
- Rule explanation entry path in this build:
  - Settings -> FAQ
- Version-scoped legal URLs for this build:
  - Terms EN: https://pearsonli.github.io/PRHelper-Legal/terms/en/v1-0-5-build4/
  - Privacy EN: https://pearsonli.github.io/PRHelper-Legal/privacy/en/v1-0-5-build4/

## ZH
发布版本：v1.0.5（build 4）
- 应用无需账号登录，核心记录与计算默认本地优先。
- 主要付费墙入口：
  1. 设置 -> 解锁专业版
  2. 免费容量超限时的新增/编辑拦截入口
  3. 家庭版未解锁时的成员切换/新增/编辑入口
- 购买/恢复/兑换路径：
  - 付费墙内订阅或买断按钮
  - 付费墙底部“恢复购买”
  - 付费墙底部“使用优惠码兑换”
- 当前授权模型：
  - 应用内授权判定以 entitlement 为准（解锁不依赖写死 product id）。
  - 月订阅有效期内：解锁 Pro + Family 能力。
  - 旧月订阅与 monthly_v2 都映射到同一 Pro entitlement，老订阅用户升级后持续可用。
  - 月订阅到期后：若无买断覆盖，Pro + Family 功能会重新锁定。
  - Pro 买断：解锁 Pro 能力。
  - Family 买断：解锁 Family 多成员能力，并包含 Pro 能力。
- 当前免费容量口径：
  - 免费版按成员计，最多 5 条总记录（旅行 + 临时居留合计）。
- 本版本临时居留入口：
  - 旅行 -> 历史记录 -> 临时居留（可折叠卡片）
- 本版本规则说明入口：
  - 设置 -> 常见问题
- 本版本法务链接：
  - 服务条款（中文）：https://pearsonli.github.io/PRHelper-Legal/terms/zh/v1-0-5-build4/
  - 隐私政策（中文）：https://pearsonli.github.io/PRHelper-Legal/privacy/zh/v1-0-5-build4/
