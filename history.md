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

# AI×分析团队转型 · 2026-09-04

## 深挖

1. **AngelList 自生长语义层**（8/28）：用 markdown 知识+Skills 替代 MetricFlow，merge 触发 manifest 自动生成 catalog，上游应用代码亦可反哺列注释。LLM 读文档写 SQL，靠 gotcha 表与展示 SQL 控错。本周试做 `AGENTS.md`+单技能+catalog 脚本。https://www.angellist.com/blog/the-semantic-layer-nobody-maintains

2. **Anthropic Slack 问数部署**（8/13）：Skills 按服务端内容每次会话重读，模型变更须同步技能；服务账号只读治理层，列级 PII 拒绝并全量打标审计。先定账号边界与结构化埋点，再扩 forecasting/cohort 等 runbook 技能。https://claude.com/blog/self-service-data-analytics-in-slack-how-anthropic-deploys-claude-tag-for-ad-hoc-questions

3. **Firebase 评测驱动 Skills**（8/11）：先写 CUJ 评测再写技能，通过率 31.7%→78.0%，并单独测技能激活率。把 Top 问数 golden set 纳入 CI，与 dbt PR 同审。https://firebase.blog/posts/2026/08/eval-driven-development-agent-skills/

4. **dbt 2026 分析工程报告**：AI 产出增速超治理成熟度；信任优先级 66%→83%，速度 50%→71%。下一阶段从生成走向执行，纪律是自治前提。用报告框架做团队「加速-治理」差距自评。https://www.getdbt.com/resources/state-of-analytics-engineering-2026

5. **Databricks AgentOps 手册**（9/2）：七阶段交付+RACI，SME 审 trace 建评测集，DevOps 三原则适配非确定性系统。选一条窄用例，用真实 trace 建 golden eval 再谈多 Agent 编排。https://www.databricks.com/blog/announcing-databricks-big-book-agentops

## 趋势

- 上下文资产（Skills/语义文档）正从「写一次」转向评测驱动 CI，与模型/表结构变更同频维护。
- AgentOps 成为可复制的运营学科：评测、可观测、成本与干系人对齐打包进交付流水线。

## 可带回团队的问题

- IM 问数 Agent 用共享服务账号时，业务方如何感知「看不见的数据边界」？
- AI 产出已加速，治理预算（评测、HITL、审计）是否按同等比例增长？

## 下期观察

- 关注 dbt 报告所述「从生成到执行」是否在 review gate 成熟前被提前上线。
