--这个文档用来存放定时的AI新闻收集

---

# AI×分析团队转型 · 2026-09-11

## 深挖

1. **Sigma 定制 Agent**（9/9）：周期分析要 scoped 数据、编排硬停止、observe→审批写入→自治、校验审计；同问不同答是常态。先锁一条周报只读+写回审批。https://www.sigmacomputing.com/blog/custom-ai-agents-data-analytics

2. **Skills→Apps**：探索用 Skill；报告固定、受众扩、token 贵时迁 UC 确定性 App，LLM 只叙述。写切换条件防 vibe 债。https://medium.com/databrickscommunity/skills-for-speed-and-learning-apps-for-trust-and-scale-924de1ee24db

3. **dbt AE 三职责**：架构（粒度/域界）、治理（测试/合约/血缘）、AI 上下文（MetricFlow）。KPI 转向语义资产维护。https://www.getdbt.com/blog/the-analytics-engineer-in-2026-system-designer-governance-owner-ai-context-provider

4. **CData 四支柱**（9/3）：身份、最小权限、策略、SIEM 审计；审查从能查表到能证明授权链。https://www.cdata.com/blog/ai-agent-data-governance

5. **Genie One 8 月**：Ontology 默认、MCP write、移动定时——问数扩至巡检写回，需 write 审批回滚。https://medium.com/@youssefmrini/whats-new-in-databricks-genie-one-august-2026-45d96c14b820

## 趋势

- Skill 探索 vs App 运营分化，缺 checklist 易堆债。
- 治理从读权限上移至行动可审计。

## 可带回团队的问题

- 哪 3 条周期报告该 Skill→App？
- 行动分级谁牵头：分析还是平台？

## 下期观察

- Databricks Glossary 对 Agent 术语消歧效果。

---

# AI×分析团队转型 · 2026-08-28

## 深挖

1. **Snowflake CoWork Automations** 把自然语言问题变成可 cron 调度的 Agent Task，每次运行生成可审计的 Cortex 线程（含 SQL、图表与 token 明细）。分析交付从被动取数转向定时 Agent 巡检；执行继承创建者权限，但 EXECUTE AGENT TASK 默认授予 PUBLIC。平台组应立刻分级回收该特权，并为业务域设 token/频率预算与上线前试跑清单。https://medium.com/snowflake/deep-dive-snowflake-cowork-automations-architecture-execution-model-and-the-agent-task-4de7b12a44b7

2. **Google Governance Agent** 借列级血缘向上游传播描述、PII 标签与质量分，为下游视图自动算信任分。Agent 时代治理瓶颈从补文档变为元数据能否随血缘自动继承。选一条核心指标链路试点 scan→apply→propagate，对比人工标注工时。https://cloud.google.com/blog/products/data-analytics/governance-on-autopilot-automate-data-governance-with-lineage

3. **HITL 数据质量门**（Petronella）：检测→分流→复核→反馈闭环，重点放在指标发布与特征组装边界。模型会自信地错，门控应拦语义漂移而非仅类型校验。为一条自动化报告链定义允许/阻断/升级三态及决策日志。https://petronellatech.com/blog/human-in-the-loop-data-quality-gates-for-ai-analytics/

4. **Thoughtworks 可靠性运营模型**：六层可靠性阶梯（术语→语义→执行等）+ Truth Contract 可执行测试。合法 SQL 仍可能在语义层失真，每层需独立责任人与失败码。给现有问数 Agent 画六层边界并补一条 contract test。https://www.thoughtworks.com/en-de/insights/blog/generative-ai/operating-model-enterprise-ai-agent-reliability

5. **Salesforce Claudeforce**（8/27）：AIforce/Headless 360 经 MCP 暴露 CRM 数据与工作流，权限沿用原 ACL，Claude 侧不保留 CRM 数据用于训练。分析 Agent 复用关键在企业 harness 而非换聊天框。盘点三条高频数据源是否具备同类权限继承的 MCP/API 接入方案。https://www.salesforce.com/ap/news/press-releases/2026/08/27/salesforce-and-anthropic-announce-claudeforce-the-1-ai-meets-the-1-ai-crm/

## 趋势

- 定时 Agent 任务成 BI 主动巡检标准原语：非确定性运行 + 线程留存改变审计与复盘方式。
- 头部 SaaS 将语义层/权限打包为 MCP harness，团队需评估「接插件」与「自建上下文层」路线。

## 可带回团队的问题

- Agent Task 默认可创建时，谁负责成本封顶、误报 SLA 与异常升级路径？
- Truth Contract 应由分析团队还是平台/Data Eng 牵头维护？

## 下期观察

- 关注 Salesforce in Claude 9 月 open beta 的 Tableau 指标接入与权限继承反馈。
