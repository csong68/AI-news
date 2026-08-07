--这个文档用来存放定时的AI新闻收集

# AI×分析团队转型 · 2026-08-07

## 深挖

1. **三平面分离：编排/计算/决策**  
生产级「数据+AI」应拆为控制面（Airflow 管状态与重试）、数据面（dbt 跑转换与测试）、决策面（LLM 只产出结构化建议）；混层是线上事故主因。  
**动作**：在现有 DAG 中强制「dbt test 失败则阻断下游 Agent」，Agent 输出 JSON 供分支，禁止 Agent 直接触发重跑。  
https://medium.com/@aidelearning/how-to-design-a-modern-data-ai-system-control-data-and-decision-planes-airflow-dbt-llm-9bf14eecb68e

2. **从 Prompt 到上下文架构**  
数据负责人实践：瓶颈不在提示词，而在 CLAUDE.md、风格指南、MCP 等「信息环境」；文档是 Agent 底表，会腐烂需定期审计。  
**动作**：选一条线性高信号流程（如 PR 审查），把隐含规范写成可版本化上下文，设只读专家 Agent + 置信度委派。  
https://bobbydenbezemer.medium.com/from-prompting-to-systems-design-lessons-from-building-ai-into-real-data-workflows-f0d1079e4dbc

3. **BA 设计三级人机监督**  
Agentic 部署需按任务选 Human-in/on/out-of-the-Loop；BA 应主导「哪些决策可自治、哪些需实时盯、哪些必须事前批准」及异常升级路径。  
**动作**：用一张表给每条 AI 工作流标注监督层级、触发升级条件与责任人，纳入需求而非上线后补。  
https://www.ba-squared.com/blog/whos-watching-the-ai-the-business-analysts-new-role-in-agentic-systems/

4. **Agent 效能看运营指标**  
Google 开源 BigQuery Agent Analytics：把请求、工具调用、错误流式入仓，支持轨迹重建、漂移检测、与业务表 JOIN 算影响。  
**动作**：为试点 Agent 定义 3 个 KPI——无人工升级解决率、平均修复时长、审计解释响应时间，替代模型跑分。  
https://cloud.google.com/bigquery/docs/bigquery-agent-analytics

5. **决策架构成为 BA 核心能力**  
IIBA 提出：Agent 可自主执行多步动作，BA 价值转向设计「可追溯、可验证」的决策链——谁有权批准、何时必须人工校验。  
**动作**：在下一个 Agent 需求里显式写出决策点、授权边界与审计字段，而非只描述界面与字段。  
https://www.iiba.org/business-analysis-blogs/ba-for-ai-agentic-ai-and-the-future-of-business-analysis/

## 趋势

- **Agent 可观测性产品化**：日志入仓、轨迹评估、漂移检测从工程自选件变为平台能力，团队应把「可审计」列为 Agent 上线门槛。  
- **分析角色上移**：从写 SQL/报告转向任务分解、上下文设计、监督模型选型——技能重心是系统设计而非工具操作。

## 可带回团队的问题

- 我们现有流水线里，控制面、数据面、决策面是否混用？Agent 有没有绕过 dbt test 直达看板的路径？  
- 每条 AI 辅助工作流，监督层级（in/on/out-of-loop）是否已书面定义并有 owner？

## 下期观察

- IIBA「Applied AI for Business Analysis」系列（9 月 16 日起）是否给出可落地的 Agent 需求模板与治理清单。

---

# AI×分析团队转型 · 2026-08-07（刊2）

## 深挖

1. **后AI分析师**（Preset）：执行被Agent压缩，价值上移至业务理解与可信自助服务设计。**动作**：选一条高频问数链，共建语义模型与复核环。https://preset.io/blog/post-ai-analyst/

2. **团队重组三决策**（Fairview）：基建当产品、划清分析vs决策、分析师上桌参与决策。**动作**：复盘议题，标注哪些改Agent吞吐+人工解读。https://getfairview.com/blog/will-ai-replace-business-analysts

3. **主动巡检**（Looker）：对话问数可固化为定时监控，超阈自动关键驱动分析推Slack。**动作**：两核心指标试点自然语言设监控。https://cloud.google.com/blog/products/business-intelligence/looker-adds-agentic-workflows-for-data-monitoring-and-insights

4. **确定性陷阱**（Dataiku）：人停止追问比模型错更危险；HITL须明确问责点。**动作**：三类高影响输出强制人工签批。https://www.dataiku.com/blog/human-in-the-loop-responsibility

5. **语义层治理围栏**（Dremio）：Agent须过统一RLS/列掩码，禁绕语义层直连。**动作**：审计并下线未走治理视图的Agent通道。https://www.dremio.com/blog/semantic-layer-governance-control-what-ai-agents-access/

## 趋势

- 分析从人跑查询转向设计Agent信任脚手架；BI从静态看板进化为 proactive 监控。

## 可带回团队的问题

- KPI仍奖励报表还是决策质量？高影响输出有无可审计问责清单？

## 下期观察

- 领域专家Agent在中小团队的复制成本。
