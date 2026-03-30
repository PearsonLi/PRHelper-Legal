---
title: Connect What's New - v1.0.7 build 2
permalink: /release/v1-0-7-build2/connect-whats-new/
---

# What's New (v1.0.7 build 2)

## EN
Release: v1.0.7 (build 2)  
Compared with v1.0.7 (build 1):
- Fixed reinstall recovery path so cloud snapshot restore no longer misses trip/PR/member/app-settings data.
- Added bootstrap protection to prevent empty local state from overwriting existing cloud backup during first-launch recovery.
- Hardened license restore + backup/restore state transitions to reduce false "not restored" outcomes right after reinstall.
- Improved member-switch consistency by isolating trip-derived computations to the selected member and enforcing transition refresh timing.

## ZH
发布版本：v1.0.7（build 2）  
相较于 v1.0.7（build 1）：
- 修复重装后的恢复链路，云端快照可恢复 trip/PR/成员与应用设置，避免只恢复部分数据。
- 新增首启保护，防止“本地空状态”在恢复期间覆盖已有云备份。
- 加强 license 恢复与备份状态切换逻辑，降低重装后短时间内误判“未恢复”的情况。
- 优化成员切换一致性：按当前成员隔离 trip 派生计算，并在切换过渡完成后触发刷新。
