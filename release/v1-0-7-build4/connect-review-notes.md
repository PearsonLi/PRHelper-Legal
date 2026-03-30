---
title: Connect Review Notes - v1.0.7 build 4
permalink: /release/v1-0-7-build4/connect-review-notes/
---

# Review Notes (v1.0.7 build 4)

## EN
Release: v1.0.7 (build 4)
- Baseline for this submission: v1.0.7 (build 3).
- No account/login is required; core tracking and calculations run locally on device.
- Main paywall entry paths remain unchanged:
  1. Settings -> Unlock Pro
  2. Free-limit interception when creating/updating records beyond capacity
  3. Family-locked member switch/add/edit paths
- Reliability scope in this build:
  - adjusted local snapshot serialization timing to reduce persistence contention,
  - retained automatic startup entitlement refresh and silent restore (no success alert).
- Reviewer sanity path:
  1. Install app, create/edit several trip/PR records quickly.
  2. Force close and relaunch.
  3. Verify records remain intact and page data stays consistent.
- Version-scoped legal URLs for this build:
  - Terms EN: https://pearsonli.github.io/PRHelper-Legal/terms/en/v1-0-7-build4/
  - Privacy EN: https://pearsonli.github.io/PRHelper-Legal/privacy/en/v1-0-7-build4/

## ZH
发布版本：v1.0.7（build 4）
- 对比基线版本：v1.0.7（build 3）。
- 应用无需账号登录，核心记录与计算默认在本地完成。
- 主要付费墙入口保持不变：
  1. 设置 -> 解锁专业版
  2. 免费容量超限时的新增/编辑拦截入口
  3. 家庭版未解锁时的成员切换/新增/编辑入口
- 本版本可靠性范围：
  - 调整本地快照序列化时机，降低持久化写入竞争；
  - 保留启动自动刷新权益与无感恢复（无“恢复成功”弹窗）。
- 审核建议路径：
  1. 安装后快速新增/编辑多条旅行与 PR 相关数据；
  2. 强制退出并重启应用；
  3. 确认数据保留完整且页面展示一致。
- 本版本法务链接：
  - 服务条款（中文）：https://pearsonli.github.io/PRHelper-Legal/terms/zh/v1-0-7-build4/
  - 隐私政策（中文）：https://pearsonli.github.io/PRHelper-Legal/privacy/zh/v1-0-7-build4/
