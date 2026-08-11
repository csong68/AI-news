--这个文档用来存放定时的AI新闻收集

# AI×分析团队转型 · 2026-08-11

## 深挖

1. **Grab：L2–L5 分析自治阶梯** — 分析团队用五级框架界定 Agent 可自主范围：L3 人定题 Agent 跑数审结论，L4 定时无人值守，L5 仅审例外。机械工单占比 Q1 44% 降至 Q2 30%，Slack 自助通道 74% 提问来自非分析岗。**动作**：选一条高频取数/根因 loop，对照 L2–L4 标注人机分界与升级触发器。[Grab 工程博客](https://engineering.grab.com/how-ai-is-transforming-analytics)

2. **Agent 就绪数仓：请求与查询间的控制层** — 传统数仓给 Agent 直连仍缺「何时可信、能否行动」边界；可靠架构需在语义层之上定义指标口径、新鲜度阈值、引用文档与动作审批，错误可逐层追溯。**动作**：为 Top10 核心指标补「决策级新鲜度 + 不可答条件」清单，纳入 Agent 上下文。[Towards Data Science](https://towardsdatascience.com/building-an-agent-ready-data-warehouse-what-traditional-architectures-do-wrong/)

3. **双层 Agent 审计：编排日志 + 上下文日志** — 仅记录 Agent 做了什么不够，还需记录「当时读了哪些已认证数据、何时、经何变换」；缺第二层则 60–70% Agent 特有风险无法覆盖。**动作**：在现有数据目录/血缘上，为 Agent 调用增加 context log 字段模板。**[Atlan 治理框架](https://atlan.com/know/ai-agent-governance/)**

4. **90 天 Agent 运营模型** — 首月建注册表：每个 Agent 有具名 Owner、风险分级与四道发布门；次月配监控包（按分级定告警频率与读者）；第三月用「无人认领 Agent」演练关停。**动作**：本周用表格列出已知 Agent，空 Owner 列当周补齐。[Progressive Robot](https://www.progressiverobot.com/2026/08/09/ai-agent-operating-model/)

5. **分析 AI 是运营基础设施，非功能插件** — 规模化靠部署前治理、全生命周期 Owner、持续评估（准确/成本/安全/可靠）作发布门，而非追模型。**动作**：把现有 BI/取数 Agent 的 SLA、回滚与事故响应写入团队 Runbook。[Okoone](https://www.okoone.com/spark/technology-innovation/ai-in-data-analytics-what-really-changes-and-how-to-get-it-right/)

## 趋势

- 分析师角色从「产出报告」转向「拥有 loop、设质量栏、审例外」——Grab 称多数成员正处于此过渡。
- 治理焦点从 GenAI 内容安全扩展到 Agent 跨系统自动动作，需 pre-dispatch 策略门而非事后抽检。

## 可带回团队的问题

- 我们团队哪些工作流已达 L3（人定题 Agent 执行），哪些仍停在 L2 辅助写 SQL？
- 每个触达生产数据的 Agent，能否在 30 秒内答出 Owner、授权范围与异常告警路径？

## 下期观察

- 新加坡 IMDA 2026 年 1 月发布的 Agentic AI 治理框架，是否成为跨团队 Agent 上线的合规参照。
