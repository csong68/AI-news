--这个文档用来存放定时的AI新闻收集

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

---

# AI×分析团队转型 · 2026-09-08

## 深挖

1. **Cube Agentic Analytics Harness**（9/3）：一年生产实践显示，问数 Agent 的可靠性取决于 harness（上下文编排、工具契约、跨会话持久化、结果校验），而非模型升级。Semantic SQL 让 Agent 在治理视图内灵活探索；工具失败须返回可恢复提示；大结果截断须明示，否则易把前 100 行样本当全集。立项时将 harness 八原则纳入设计评审清单。https://cube.dev/blog/building-an-agentic-analytics-harness

2. **Chalk 实时上下文**（9/5）：Agent 有效上下文本质是「请求时刻的快照」，依赖 cron 物化的窗口特征在多步推理中易静默过期。扑克示例说明聚合须按决策 instant 计算，延迟等同无数据。为核心问数链路定义数据新鲜度 SLA，超时则拒答或升级人工。https://chalk.ai/blog/context-has-a-timestamp

3. **Fabric Data Agents GA**（9/3）：微软将 Data Agent 定位为「领域虚拟分析师」，经 Fabric IQ 语义层 grounding，可同时查仓内指标与 PDF/文档中的业务规则；整 Agent 可暴露 MCP 端点供 Copilot/外部编排调用。选一个「数在仓、规在文档」的高频业务域评估试点 ROI。https://www.jamesserra.com/archive/2026/09/microsoft-fabric-data-agents-bringing-structured-and-unstructured-data-together/

4. **Agents Playbook 三层评测**：确定性断言在 CI 拦契约违规 → LLM-as-judge 按 rubric 评主观质量 → 生产监控采集编辑/重生成/升级等隐式信号。用户改稿距离是免费且高信噪的质量梯度，应回流为 golden case。为问数 Agent 沉淀首批 10 条评测用例并设 PR 合并门禁。https://playbook.agentskit.io/docs/pillars/quality/agent-eval-framework-pattern

5. **Braintrust 多步 Agent 评测**：须 trace 记录逐步工具选择与参数；评测嵌入 CI/CD，PR 自动跑 golden set 并标注回归项。分析团队可将「指标口径断言 + SQL 结构校验」设为 Tier1 确定性门禁，再叠加 LLM judge。https://www.braintrust.dev/articles/ai-agent-evaluation-framework

## 趋势

- 分析 Agent 竞争焦点正从模型能力转向 harness 与上下文工程，语义层是底座而非全部。
- 「上下文有时间戳」：实时特征 serving 渐成问数准确性的隐性前置，仅靠批处理物化不够。

## 可带回团队的问题

- 混合文档+指标问答时，文档 grounding 的权责划分与审计链如何设计？
- 用户改稿/重生成率是否应纳入分析师 SLA，并驱动 Agent 迭代 backlog？

## 下期观察

- 关注 Cube 8 条 harness 设计原则文档发布后的企业落地反馈。
