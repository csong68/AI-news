--这个文档用来存放定时的AI新闻收集

---

# AI×分析团队转型 · 2026-08-14

## 深挖

1. **语义层 vs 直写 SQL** dbt 2026 基准：Text-to-SQL 复杂场景仍可能返回「合理但错误」数字；语义层覆盖内近 100% 且无法回答时会拒答。**动作**：OKR/董事会走语义层，探索性提问先查覆盖再降级 SQL。 https://docs.getdbt.com/blog/semantic-layer-vs-text-to-sql-2026

2. **AI 加速交付更要收紧规划** Analytics8：周期压缩后目标漂移风险升；考核从吞吐量转向嵌入决策的可衡量影响。**动作**：试点启动时写清业务结果指标与验收问题集。 https://www.analytics8.com/blog/ai-and-data-strategy-in-2026-what-leaders-need-to-get-right/

3. **30 天就绪冲刺** Kaelio：就绪=指标+上下文+权限+评测+运营；收 25–50 个真实问题作评测集，按真实角色测权限。**动作**：四周定域→核指标→补术语/示例→单界面灰度。 https://www.kaelio.com/blog/ai-analytics-readiness-checklist-for-data-leaders

4. **管道质量环先于 Agent** Databricks：治理与管道须并行，变更自动校验行数/分布，异常在触达模型前拦截。**动作**：选一条高价值管道接入与 AI 相同的 CI 质量门。 https://www.databricks.com/blog/ai-and-data-transformation

5. **MCP 连通先于编排** Analytics8：MCP 管连接，Agent 管编排；无统一 KPI 时 NL 查询放大口径冲突。**动作**：先收敛高频 KPI 到语义层再开对话入口。 https://www.analytics8.com/blog/ai-and-data-strategy-in-2026-what-leaders-need-to-get-right/

## 趋势

- 竞争焦点从「会不会写 SQL」转向「出错能否拒答、能否审计」。

## 可带回团队的问题

- 董事会数字多少走语义层、多少靠临时 SQL？
- AI 减半交付周期后，业务验收标准是否同步收紧？

## 下期观察

- verified/golden queries 运营模板能否跨团队复用。
