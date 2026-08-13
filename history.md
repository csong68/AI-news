--这个文档用来存放定时的AI新闻收集

---

# AI×分析团队转型 · 2026-08-13

## 深挖

1. **EU AI Act 高风险管理义务已生效（8月2日）**：分析团队若在招聘、信贷、风控等 Annex III 场景部署 Agent，须按「义务→控制→证据」五链持续运营，含系统清单、风险分级、人工监督与至少六个月日志；NIST/ISO 42001 控制可一次映射多框架。动作：本周盘点团队内所有分析类 AI（含 BI 内嵌能力与 shadow 工具）并标注 deployer/provider 角色。https://aisigil.com/ai-compliance/

2. **Google Conversational Analytics 全面 GA**：BigQuery/Looker CA API 正式可用，支持 Agentic Workflows 主动巡检异常、经 MCP/ADK 嵌入 Slack 等多 Agent 编排，并用 OTEL 导出健康/延迟/token 指标。动作：把「对话日志+OTEL 指标」纳入分析 Agent 运营 KPI，而不只看回答准确率。https://cloud.google.com/blog/products/data-analytics/conversational-analytics-in-google-data-cloud-in-q326

3. **分析师转向「上下文工程师」（Hiflylabs 实践）**：交付从线性串行改为 Initiate（需求结构化入上下文层）→ Build Loop（Agent 搭模型/报告、人审每一步）→ Productionize（上下文即文档）；项目实测交付成本降约 60%、洞察时效约 10 倍。动作：选一个高价值报表试点，先写 KPI/实体 markdown 上下文再开 Agent 建模。https://hiflylabs.com/blog/2026/4/21/agentic-bi-claude-context-workflows

4. **分析平台四阶段演进（Dataiku）**：Stage 3「模型与决策割裂」是多数团队瓶颈；Stage 4 要求模型/Agent 嵌入审批工作流且治理内建于部署架构。动作：用「能否在单一 Flow 内完成取数→建模→Agent→审批」评估现有平台，而非只看仪表盘能力。https://www.dataiku.com/blog/enterprise-analytics-platforms

5. **Agentic Analytics 语义层接口化（Cube）**：Agent 经 MCP 按指标名请求已认证度量，编译期施加行级安全，避免直写 raw SQL。动作：为 Top 20 核心指标建立单一语义定义并开放 MCP，作为团队 Agent 唯一取数入口。https://cube.dev/articles/what-is-agentic-analytics

## 趋势

- 分析从「人提问」转向「Agent 主动巡检+深潜归因」，平台需同时提供语义 grounding 与可观测性。
- 合规窗口已开：高风险管理从事后清单变为持续证据链运营，分析团队需承担 deployer 职责。

## 可带回团队的问题

- 我们的分析 Agent 是否已纳入 AI 系统清单并完成 EU 风险分级？
- 分析师工时有多少花在「上下文建设」而非重复 SQL/修报表？

## 下期观察

- ISO 42001 认证与 EU AI Act 控制映射的落地案例
