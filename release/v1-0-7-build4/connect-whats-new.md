---
title: Connect What's New - v1.0.7 build 4
permalink: /release/v1-0-7-build4/connect-whats-new/
---

# What's New (v1.0.7 build 4)

## EN
Release: v1.0.7 (build 4)  
Compared with v1.0.7 (build 3):
- Improved local persistence scheduling so data serialization runs on a debounce callback instead of blocking immediate UI interactions.
- Reduced risk of transient data-loss behavior during rapid create/edit workflows by consolidating snapshot-write timing.
- Kept automatic background restore behavior (no success alert) and release-scoped legal links for this build.

## ZH
发布版本：v1.0.7（build 4）  
相较于 v1.0.7（build 3）：
- 优化本地持久化写入时机，将序列化放到防抖回调执行，减少对即时 UI 操作的阻塞。
- 合并快照写入节奏，降低高频新增/编辑场景下出现瞬时数据不一致或丢失的风险。
- 保留启动后后台自动恢复购买（无成功弹窗）与本版本专用法务链接策略。
