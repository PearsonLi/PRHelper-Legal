---
title: Connect Review Notes - v1.0.7 build 2
permalink: /release/v1-0-7-build2/connect-review-notes/
---

# Review Notes (v1.0.7 build 2)

## EN
Release: v1.0.7 (build 2)
- No account/login is required; core tracking and calculations run locally on device.
- Main paywall entry paths remain:
  1. Settings -> Unlock Pro
  2. Free-limit interception when creating/updating records beyond capacity
  3. Family-locked member switch/add/edit paths
- This build focuses on reinstall recovery correctness and member-scoped data consistency:
  - cloud restore bootstrap guard to avoid empty snapshot overwrite,
  - full restore path for trip/PR/member/app settings,
  - license restore stabilization on first launch,
  - member-scoped trip derivation and transition refresh ordering.
- Reviewer sanity path for this build:
  1. Install app, create sample travel/member/PR settings, then uninstall and reinstall.
  2. Launch app with iCloud available and wait for automatic restore.
  3. Verify trip history, PR settings, member settings, and license state are restored without manual import.
  4. Switch members and verify overview/travel/PR/citizenship pages refresh to selected member data.
- Version-scoped legal URLs for this build:
  - Terms EN: https://pearsonli.github.io/PRHelper-Legal/terms/en/v1-0-7-build2/
  - Privacy EN: https://pearsonli.github.io/PRHelper-Legal/privacy/en/v1-0-7-build2/

## ZH
发布版本：v1.0.7（build 2）
- 应用无需账号登录，核心记录与计算默认在本地完成。
- 主要付费墙入口保持不变：
  1. 设置 -> 解锁专业版
  2. 免费容量超限时的新增/编辑拦截入口
  3. 家庭版未解锁时的成员切换/新增/编辑入口
- 本版本重点为“重装恢复正确性 + 成员作用域一致性”：
  - 首启恢复期间阻止空快照覆盖云端，
  - trip/PR/成员/应用设置的完整恢复链路，
  - 首次启动时 license 自动恢复稳定性增强，
  - 按当前成员作用域计算并在切换后完成刷新。
- 审核建议路径：
  1. 安装应用并创建旅行/成员/PR 设置样例数据后卸载重装；
  2. 在 iCloud 可用条件下启动应用，等待自动恢复；
  3. 确认 trip、PR 设置、成员设置和 license 状态均可自动恢复，无需手动导入；
  4. 切换成员后，确认 overview/travel/PR/citizenship 页面刷新为当前成员数据。
- 本版本法务链接：
  - 服务条款（中文）：https://pearsonli.github.io/PRHelper-Legal/terms/zh/v1-0-7-build2/
  - 隐私政策（中文）：https://pearsonli.github.io/PRHelper-Legal/privacy/zh/v1-0-7-build2/
