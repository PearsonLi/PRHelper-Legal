---
title: Connect Review Notes - v1.0.7 build 3
permalink: /release/v1-0-7-build3/connect-review-notes/
---

# Review Notes (v1.0.7 build 3)

## EN
Release: v1.0.7 (build 3)
- Baseline for this submission: v1.0.7 (build 2).
- No account/login is required; core tracking and calculations run locally on device.
- Main paywall entry paths remain:
  1. Settings -> Unlock Pro
  2. Free-limit interception when creating/updating records beyond capacity
  3. Family-locked member switch/add/edit paths
- This build is a reliability patch focused on backup/restore behavior:
  - backup/restore internals are aligned back to the stable v1.0.6 build 1 architecture,
  - startup automatically refreshes purchase entitlement and applies restore silently,
  - no user-facing success alert is shown for restore completion,
  - release-scoped legal links are updated to build 3 URLs.
- Reviewer sanity path for this build:
  1. Install app, create sample travel/member/PR settings, then force close and relaunch.
  2. Verify data is retained after relaunch.
  3. Uninstall and reinstall with iCloud available; launch app and wait for automatic restore.
  4. Verify trip history, PR settings, member settings, and license state are restored without manual import.
- Version-scoped legal URLs for this build:
  - Terms EN: https://pearsonli.github.io/PRHelper-Legal/terms/en/v1-0-7-build3/
  - Privacy EN: https://pearsonli.github.io/PRHelper-Legal/privacy/en/v1-0-7-build3/

## ZH
发布版本：v1.0.7（build 3）
- 应用无需账号登录，核心记录与计算默认在本地完成。
- 主要付费墙入口保持不变：
  1. 设置 -> 解锁专业版
  2. 免费容量超限时的新增/编辑拦截入口
  3. 家庭版未解锁时的成员切换/新增/编辑入口
- 本版本为“备份/恢复可靠性补丁”：
  - 备份/恢复内部实现回退到 v1.0.6 build 1 的稳定架构，
  - 启动时自动刷新购买权益并后台执行恢复，
  - 不再弹出“恢复成功”提示框，
  - 法务链接统一更新到 build 3 对应页面。
- 审核建议路径：
  1. 安装应用并创建旅行/成员/PR 设置样例数据后强制退出并重启；
  2. 确认重启后数据仍保留；
  3. 在 iCloud 可用条件下卸载重装并启动应用，等待自动恢复；
  4. 确认 trip、PR 设置、成员设置和 license 状态均可自动恢复，无需手动导入。
- 本版本法务链接：
  - 服务条款（中文）：https://pearsonli.github.io/PRHelper-Legal/terms/zh/v1-0-7-build3/
  - 隐私政策（中文）：https://pearsonli.github.io/PRHelper-Legal/privacy/zh/v1-0-7-build3/
