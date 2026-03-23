---
title: Version Change Log
permalink: /release/version-change-log/
layout: legal
hero_title: 版本需求与变更清单
hero_subtitle: 从首个提审版本开始，所有需求、代码变更与测试用例一一对应。
last_updated: 2026-03-03
---

# 枫叶卡管家：版本需求与变更清单

## 使用规则（强制）

1. 从首个提审版本开始，每个版本都必须记录“需求 -> 变更 -> 测试用例”映射。
2. 任何功能/逻辑/UI 改动都必须新增或更新测试用例，并在表格中写明测试文件路径。
3. 发布前执行：

```bash
npm run check:change-log
```

如果缺少变更记录或缺少测试映射，命令会失败并阻断发布。

---

## v1.0.0（首个提审版本）

| Change ID | 需求 Requirement | 变更 Change | 测试用例 Test Cases |
|---|---|---|---|
| V100-001 | 首个提审版本稳定性门禁 | 建立历史错误回归矩阵与发布全链路测试 | `tests/functional/releaseHistoricalRegression.functional.test.ts`; `tests/functional/systemMatrix3000.functional.test.ts`; `tests/performance/residencyRules.performance.test.ts`; `e2e/maestro/flows/smoke_all_pages.yaml` |

---

## vNext（待发布）

| Change ID | 需求 Requirement | 变更 Change | 测试用例 Test Cases |
|---|---|---|---|
| VNEXT-001 | 版本变更台账与测试绑定机制 | 新增版本变更清单、自动校验脚本，并接入发布门禁 | `tests/unit/verifyChangeLogGuard.unit.test.ts` |
| VNEXT-002 | Paywall 支持 iOS 下滑关闭且购买中禁止误关闭 | Paywall 改为 pageSheet + slide，增加顶部下拉指示条，购买流程中禁用手势关闭 | `tests/unit/paywallDismissPolicy.unit.test.ts` |
| VNEXT-003 | 设置页增加导入导出入口，旅行页移除导出入口 | 在 Settings 功能区新增“导入导出”子页（含导出旅行记录按钮）；移除 Trip 页顶部导出按钮，避免入口重复 | `tests/unit/settingsImportExportPlacement.unit.test.ts` |
| VNEXT-004 | 日期选择器年份默认需居中显示当前已选年份（或今天年份） | 新增年份条自动居中逻辑，打开年月面板后自动滚动至目标年份居中，并固定年份 chip 宽度稳定计算 | `tests/unit/datePickerYearCentering.unit.test.ts` |
| VNEXT-005 | 日期组件默认展开年/月选择面板 | 打开日期组件时默认展开年/月区域，减少额外点击 | `tests/unit/datePickerYearCentering.unit.test.ts` |
| VNEXT-006 | 日期输入期间需持续展示完整年/月/日面板 | 内联日期选择器在打开期间强制保持年/月/日展开，仅在“取消/确定”后关闭，避免输入中途自动折叠 | `tests/unit/datePickerPersistentExpanded.unit.test.ts` |
| VNEXT-007 | 设置页新增 General 并接入主题切换，导入导出标记开发中 | Settings 功能区新增 General 子页（语言/输入模式开发中/7 套主题）；导入导出改名为“旅行记录导入导出”并标记“火热开发中”；Paywall 增加“旅行记录导入和导出（开发中）”“家庭管理（开发中）” | `tests/unit/settingsImportExportPlacement.unit.test.ts`; `tests/unit/paywallFeatureFlags.unit.test.ts`; `tests/unit/themeRegistry.unit.test.ts` |
| VNEXT-008 | 永居/入籍页面标题文案统一为风险预警 | 将“风险预测 / Risk forecast”统一替换为“风险预警 / Risk alerts”，确保中英文术语一致 | `tests/unit/riskLabelText.unit.test.ts` |
| VNEXT-009 | 主题选择精简为 3 套风格 | 仅保留“经典沉浸（黑色）”“梵高·星空”“宫崎骏·自然治愈”三套主题，并按新配色参数重建 token | `tests/unit/themeRegistry.unit.test.ts` |
| VNEXT-010 | 主题配色按指定色板精准对齐 | 梵高主题与宫崎骏主题按用户指定主色/背景/文本/强调色/表面色精确落地，补充锚点色值测试 | `tests/unit/themeRegistry.unit.test.ts` |
| VNEXT-011 | 修复宫崎骏主题总览顶部黑卡未切换 | 去除总览顶部卡片黑色兜底色，强制走主题主色；宫崎骏主题主卡前景色与文本对比度按主题 token 对齐 | `tests/unit/themeRegistry.unit.test.ts` |
| VNEXT-012 | 全页面按钮与设置菜单主题联动 | 新旅行/保存/取消/设置页按钮与 Paywall CTA、设置菜单图标和文字颜色统一改为 theme token 驱动，避免固定黑色 | `tests/unit/themeRegistry.unit.test.ts`; `tests/unit/paywallFeatureFlags.unit.test.ts` |
| VNEXT-013 | 主题发布锁定为经典沉浸（黑色） | 保留三套主题设计代码，但仅开放经典沉浸可选；其余主题在设置中禁用并标注“开发中”，运行时若读到非经典主题自动回退经典 | `tests/unit/themeSelectionGate.unit.test.ts` |
| VNEXT-014 | 首次安装改为强制隐私条款同意 + 可选初始化配置 | 首次使用增加语言、旅行输入模式（第二种开发中）、永居登陆日/有效期配置入口；仅“同意隐私与条款”为必选，未勾选不可开始；配置后仍可在设置修改 | `tests/unit/onboardingConsentGate.unit.test.ts` |
| VNEXT-015 | 设置页上线旅行记录导入导出（JSON 备份 + PDF 报告）并与手工录入校验逻辑统一 | 新增 `DataManagementScreen.tsx`（说明/导入预览/确认导入/JSON 导出/PDF 导出）；导入使用与手工录入相同 overlap 校验入口；Paywall 与 Terms/Privacy 同步更新导入导出能力描述 | `tests/unit/dataManagementScreen.unit.test.ts`; `tests/unit/residencyStore.unit.test.ts`; `tests/unit/paywallFeatureFlags.unit.test.ts`; `npm run test:functional`; `npm run test:performance` |
