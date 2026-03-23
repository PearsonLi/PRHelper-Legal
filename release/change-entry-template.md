# 变更条目模板（每次改动必填）

将以下一行追加到 `docs/release/version-change-log.md` 的 `vNext（待发布）` 表格中：

```md
| VNEXT-XXX | <本次需求> | <代码/逻辑/UI具体变更> | `tests/unit/xxx.test.ts`; `tests/functional/xxx.test.ts` |
```

填写要求：

1. `需求`：用一句话描述用户需求或问题背景。
2. `变更`：描述实际实现内容（不要只写“优化”）。
3. `测试用例`：必须填写至少 1 个测试文件路径，且文件实际存在于仓库。
4. 若是规则变更，至少补充 1 个功能测试或回归测试，不可只改 UI 冒烟。
