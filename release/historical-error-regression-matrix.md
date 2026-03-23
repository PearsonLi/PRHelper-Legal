---
title: Release Regression Matrix
permalink: /release/historical-error-regression-matrix/
layout: legal
hero_title: 历史错误回归矩阵（发布门禁）
hero_subtitle: 把历史问题固化为测试门禁，保证提审版本稳定性。
last_updated: 2026-03-02
---

# 枫叶卡管家：历史错误回归矩阵（发布门禁）

> 目标：把开发过程中反复出现的问题固化为自动化测试，发版前统一执行，避免回归。

## 发布前一键执行

```bash
npm run test:release:full
```

该命令会执行：
- TypeScript 类型检查
- 历史错误回归测试集
- 全量单元/功能/性能测试
- RevenueCat 生产 Offering 连通性检查
- Maestro UI 冒烟回归

并在 `tests/reports/release_gate/` 生成报告。

## 错误 -> 回归用例映射

| 编号 | 历史错误（已发生） | 回归策略 | 自动化用例 |
|---|---|---|---|
| REG-001 | PR 登陆不足 5 年时，统计起点误用 5 年窗口起点 | 校验 PR/入籍起点使用 `max(rollingStart, prLanding)` | `tests/functional/releaseHistoricalRegression.functional.test.ts` |
| REG-002 | ongoing 行程（未填入境）把未来天数也算成离境 | 强制 ongoing 在实际统计仅算到 today | `tests/functional/releaseHistoricalRegression.functional.test.ts` |
| REG-003 | 未来旅行计划未纳入趋势预测 | 预测引擎必须包含 planned 记录 | `tests/functional/releaseHistoricalRegression.functional.test.ts` |
| REG-004 | ongoing 未闭环时仍可插入新记录 | 将 ongoing 视为无限远终点参与冲突检测 | `tests/functional/releaseHistoricalRegression.functional.test.ts` + `tests/unit/validateRecordOverlap.unit.test.ts` |
| REG-005 | 相邻区间被误判重叠 | 重叠判断允许 end+1 与 nextStart 相邻 | `tests/functional/releaseHistoricalRegression.functional.test.ts` + `tests/unit/validateRecordOverlap.unit.test.ts` |
| REG-006 | 更新已有记录时被自己冲突拦截 | 更新/确认草稿时排除自身 ID | `tests/functional/releaseHistoricalRegression.functional.test.ts` + `tests/unit/residencyStore.unit.test.ts` |
| REG-007 | 缺少出境提示误报（窗口边界日） | 校验 `start == windowStart` 不计为缺少出境 | `tests/functional/releaseHistoricalRegression.functional.test.ts` + `tests/unit/travelMatching.unit.test.ts` |
| REG-008 | 当前境外 ongoing 被误报缺少入境 | 当前境外且跨 today 的范围不触发 missing-entry | `tests/functional/releaseHistoricalRegression.functional.test.ts` + `tests/unit/travelMatching.unit.test.ts` |
| REG-009 | 草稿记录影响正式统计 | 统计引擎只处理 `isConfirmed === true` | `tests/functional/releaseHistoricalRegression.functional.test.ts` + `tests/unit/timelineProjection.unit.test.ts` |
| REG-010 | 同一日多事件（手工/自动）口径不一致 | 手工优先、官方口径默认在加规则 | `tests/functional/systemMatrix3000.functional.test.ts` + `tests/unit/presenceCounting.unit.test.ts` |
| REG-011 | PR 特殊场景误计入入籍 | PR special 仅计入 PR，不计入 citizenship | `tests/unit/presenceCounting.unit.test.ts` + `tests/functional/systemMatrix3000.functional.test.ts` |
| REG-012 | 日期解析不严格导致误算 | 仅接受严格 `YYYY-MM-DD` | `tests/functional/systemMatrix3000.functional.test.ts` |
| REG-013 | 时区边界导致 ±1 天误差 | 统一本地日历日 start-of-day 运算 | `tests/functional/systemMatrix3000.functional.test.ts` + `tests/unit/residencyRules.unit.test.ts` |
| REG-014 | 预测图性能慢、移动端卡顿 | 30 天采样 + 关键点策略 + 性能回归 | `tests/performance/residencyRules.performance.test.ts` + `tests/unit/timelineProjection.unit.test.ts` |
| REG-015 | UI 功能改动后导航/核心流程断链 | 每次发版跑 Maestro 全页面冒烟 | `e2e/maestro/flows/smoke_all_pages.yaml` |
| REG-016 | RevenueCat 配置误用测试 Key/Offering 缺失 | 发布门禁增加生产 Offering 检查 | `scripts/check-revenuecat-offering.mjs`（由 `test:release:full` 调用） |

## 人工检查项（无法完全自动化）

- 真机 Apple IAP 付款链路（沙盒账号、弱网、恢复购买）
- App Store Connect 元数据/IAP 绑定关系
- 多机型视觉细节（小屏字号、图层遮挡、触控热区）

上述三项保留在提审前人工清单中执行。
