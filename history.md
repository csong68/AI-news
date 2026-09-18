--这个文档用来存放定时的AI新闻收集

---

# AI×分析团队转型 · 2026-09-18

## 深挖

1. **叙述性完成**（9/17）：Agent 会说「已完成」却未调用工具——比报错更隐蔽。确认必须来自工具回执；`pending_approval` 不得粉饰为成功。问数/报告链加规则：无 tool receipt 禁止标 done。https://thecolony.ai/post/a4ff48a8-3665-44a8-a06b-af3fe243de67

2. **ground-truth-as-code**（9/15）：周期 KPI 答案随数据漂移，静态 golden 易失效。期望答案写成可执行参考函数，评测时从 live 数据重算再 factoid 比对。选 3 个周报指标试点 reference function。https://arxiv.org/abs/2609.16487

3. **Symbolic Separation**（9/15）：多步运营问数常败于 LLM 臆造表间关系。Agent 自由推理，取数只能经本体约束 VKG 预校验，把 join 变成图遍历。多源场景优先语义/本体路径。https://arxiv.org/abs/2609.17107

4. **ChatGPT 问数分层**（9/16）：Data Agent 连仓建板依赖 dbt/语义层与仓内权限；OpenAI 内部可用因先有共享指标、访问规则与复核流程。用五问清单评估就绪度。https://www.toucantoco.com/en/blog/chatgpt-for-data-analysis

## 趋势

- 分析 QA 从判答案扩展到验执行链路与工具回执。
- 非平稳指标的 golden set 正向可执行 ground truth 迁移。

## 可带回团队的问题

- 现有问数/报告 Agent 是否会出现「口头完成」？门禁在哪？
- 哪些周期 KPI 适合率先改成 ground-truth-as-code？

## 下期观察

- Thoughtworks AIRD Part 2（数据运营化故事）。

---

# AI×分析团队转型 · 2026-09-15

## 深挖

1. **Thoughtworks AIRD**（9/14）：缺目录/语义层，问数 Agent 像无标签超市问路。选一条核心指标讲清「无目录=不可用」。https://www.thoughtworks.com/insights/blog/machine-learning-and-ai/ai-ready-data-part-1

2. **EY 运营模型**（9/4）：价值在端到端重设计；82% 忧 token 成本，64% 有预算监控。先定 ROI 再配预算。https://www.reworked.co/digital-workplace/what-the-ai-era-operating-model-actually-looks-like/

3. **人机 Agent 运营**（8/19）：系统地图标域主+用例；三档自治，影子运行后才扩权。https://nikhil-chandna71.medium.com/the-human-agent-operating-model-for-the-enterprise-f5c58c8cc057

4. **多模型 QA 环**：生成-审查-裁决分离，证据不足阻断发布。周报接入第二模型审稿。https://data-analysis.cloud/how-multi-model-ai-review-loops-can-improve-analytics-report

5. **BA 归属瓶颈**：Agent 写初稿后瓶颈在「谁署名」；交付物是具名复核。试点强制 reviewer 字段。https://medium.com/@squalliahmed/how-the-technical-business-analyst-role-changes-when-agents-write-the-first-draft-f8be9cd27384

## 趋势

- 治理嵌入工作流：80–90% 标准化、例外才人工。
- 分析 QA 转向多模型分工。

## 可带回团队的问题

- 能否用「数据超市」故事说清 AIRD 优先级？
- Agent 产出谁署名复核？缺字段能否拦截？

## 下期观察

- Thoughtworks AIRD Part 2。

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
