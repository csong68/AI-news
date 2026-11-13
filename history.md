--这个文档用来存放定时的AI新闻收集

---

# AI×分析团队转型 · 2026-11-13

## 深挖

1. **Genie 全语境**（11/11）：同一对话内结构化表与 UC Volume 文档并重，页级引用且受权限约束。选一条「表+合同/纪要」混合问法试点，无引用不得对外。https://www.databricks.com/blog/enterprise-context-action-genie-agents-now-analyze-more-data-sources-transform-your-work

2. **连接器白名单**（11/11）：MCP GA，作者按 Agent 勾选 Slack/Jira 等读写能力，经 Unity Gateway 统一治理。为 2 个域 Agent 列只读与可写工具矩阵并评审。https://www.databricks.com/blog/enterprise-context-action-genie-agents-now-analyze-more-data-sources-transform-your-work

3. **BigQuery measures GA**（11/10）：指标与关系图合一 Property Graph，grain-lock 避免 join 重复计数，Catalog 可检索同义词。挑 1 个需「what+why」的周例会问题映射图模型。https://cloud.google.com/blog/products/data-analytics/bigquery-measures-ga-unifying-bi-metrics-and-knowledge-graphs

4. **仓内预置上下文**（11/11）：检索与分块一次入仓复用，减多 MCP 与长 payload；dbt 实践 token 降逾 50%。高频访谈/工单摘要改 dbt 表+单入口 MCP。https://www.getdbt.com/blog/economic-case-warehouse-first-ai-context

5. **Agent 就绪沟**（11/10）：41% 已上生产 Agent，仅 15% 自认数据底座够；成熟度在语义/血缘非模型档位。用自评与现网 Agent 清单对齐 Q1 能力项。https://www.getdbt.com/blog/ai-maturity-trusted-data-to-trusted-ai-agents

## 趋势

- 分析 Agent 从单仓 SQL 走向「表+文档+协作工具」闭环，效能指标需加入连接器与引用审计。

## 可带回团队的问题

- 文档语境是否纳入问数验收（无页码/无权限校验则不放行）？
- Agent 把查询量放大时，成本预算按人头还是按会话/工具调用计量？

## 下期观察

- Lakehouse//RT 在 Agent 高并发下的账单与 SLA 对照案例（11/12 厂商叙事待第三方验证）。

---


# AI×分析团队转型 · 2026-11-10

## 深挖

1. **QueryData 契约**（11/4）：运营库 Agent 用模板、facet、值解析做消歧合成，与分析仓 Knowledge Catalog context set 分工不同。业务库先配十类高频问模板。https://docs.cloud.google.com/gemini/data-agents/querydata

2. **上下文爬坡**（11/5）：Context Engineering Agent 用金题 hill-climb 补模板/facet，上下文可进 Git。定 15 道金题与版本门槛。https://docs.cloud.google.com/gemini/data-agents/querydata/sql-postgres/build-context-sets

3. **AI in BI 门禁**（11/8）：先语义层+评测+复核再开聊天；身份透传、域内指标、只读，日志记问题/指标/SQL。三 personas 测 RLS。https://duces.co/blog/ai-in-bi-semantic-layer

4. **Business Ontology**（11/3）：Sense 推断、Ontology 人审、Semantic Views 固定算式。3 个跨域 KPI 指定 ontology steward。https://www.snowflake.com/en/blog/business-ontology-context/

5. **意图-SQL 分界**（11）：NL 到语义意图，SQL 由引擎确定生成；token 验指标免审 SQL。评审上移到语义模型。https://docs.thoughtspot.com/cloud/26.11.0.cl/semantic-layer

## 趋势

- 语义资产从指标目录变为可执行契约：canonical 问法、join 与取值规则进入查询路径。

## 可带回团队的问题

- 运营库与分析仓的 context set 合并还是分域治理？
- 错题能否按缺模板/缺 facet/口径冲突分类改进？

## 下期观察

- QueryData preview 与 secure view 行权限联动的实践反馈。

---

# AI×分析团队转型 · 2026-11-06

## 深挖

1. **CoCo 进 Excel/Sheets**（11/5）：表内建公式/透视，SQL 存 workbook 可刷新，RLS 随角色；接 Semantic Views。CSV 快照→ live 模型。选一条手工导出周报试点。https://www.snowflake.com/en/blog/snowflake-coco-microsoft-excel-google-sheets/

2. **语义联邦 GA**（10/29）：LookML/dbt/Snowflake 语义视图进同一 context graph，冲突口径并排溯源。复用既有定义而非新 prompt。盘点 5 个 KPI 多源冲突。https://cloud.google.com/blog/products/data-analytics/expanded-semantic-model-support-in-knowledge-catalog

3. **LangChain 上下文**（10/27）：描述→guides→语义层→endorsement 约 40× 自助问数；endorse 滥发则可信信号失效。1 份业务 guide 进 repo+CI 同步。https://www.getdbt.com/blog/langchain-self-serve-analytics-ai-agent-context

4. **Meta:Context**（10/26）：解读语境跟 metric 同 YAML 走 PR；缺 card 则根因分析无据。为 2 个易误读 KPI 写 card。https://www.getdbt.com/blog/meta-context-dbt-semantic-layer-business-context

## 趋势

- 分析 AI 迁入 Excel/Sheets，产物是可刷新 workbook 非对话截图。
- Catalog 推 context set 自学习；开量前先定人审门槛（11/4）。

## 可带回团队的问题

- 还有多少「影子 CSV」可用 workbook 内嵌 SQL+刷新替代？
- dbt 与 BI 口径不一致时，Agent 上线前谁对账？

---

# AI×分析团队转型 · 2026-11-03

## 深挖

1. **Snowflake 受限会话**（10/30）：Agent 继承用户权限仍可能误删表或触 PII；RSS 为 Agent 会话设权限天花板（可禁角色、限写沙箱）。平台组发布默认 RSS 并纳入 onboarding。https://www.snowflake.com/en/blog/engineering/control-what-ai-agents-can-do-in-your-snowflake-sessions/

2. **DataHub beta**（10/28）：裸接仓约 40% 准；全库暴露更差。先单域 golden eval，再叠技术/语义/知识层，Miro 约 90%。本周锁一域+十题基线再扩。https://datahub.com/blog/making-ai-agents-trustworthy-lessons-from-beta/

3. **Careem 验真 PR**（10/26）：生成容易、合并在验；spec-lock 歧义指标，沙箱 compile/test 自修复至绿才提 PR。把口径追问写进 intake 模板。https://www.getdbt.com/blog/careem-ai-dbt-model-testing-validation

4. **dbt Skills 评估**（10/30）：22 轮 ticket 显示方差来自流程非技能；Skills 宜留团队 deploy/review 与 Mesh 等冷门栈。eval 测 backup 与定义遵守。https://docs.getdbt.com/blog/do-coding-agents-still-need-dbt-skills

## 趋势

- 问数 Agent 权限从「等于用户」改为会话级降权。
- 上下文从一次性文档转向 eval 驱动的持续运营。

## 可带回团队的问题

- 仓侧 Agent 是否已有低于用户的默认权限边界？
- 能否用十道域内金题量化「加一层上下文」的边际收益？

## 下期观察

- DataHub Context GA 对 context 分工的落地反馈。

---

# AI×分析团队转型 · 2026-10-27

## 深挖

1. **BI「为什么错」**（10/26）：Copilot 只复述错标签，难追 dbt CASE。三 MCP 分专 Agent，六分钟三问附校验 SQL。查根因链缺哪环。https://www.getdbt.com/blog/mcp-ai-agent-dashboard-debugging

2. **评测驱动**（10/26）：裸表 0%→verified 94.7%，增益在语义层非换模型。测不准不上线，golden 套件分层加料。https://www.getdbt.com/blog/data-culture-ai-analytics-agent-trust-context

3. **LookML 入 Catalog GA**（10/26）：公式/Join/血缘进 context graph 并近实时同步。Agent 须拿确定性定义。https://cloud.google.com/blog/products/business-intelligence/lookml-metadata-indexing-in-knowledge-catalog-is-now-ga/

4. **超越采纳**（10/23）：同等交互可能是查概念或建管道；分基础/应用/Agentic 看产能。周报加工作类型。https://www.snowflake.com/en/blog/measure-ai-value-beyond-adoption/

5. **Wizard 验 DAG**（10/26）：人判 downstream 影响非 diff；dev 先验再合并，incident 降 15–20%。https://www.getdbt.com/blog/dbt-wizard-ai-agent-validation-lineage

## 趋势

- 排查从 BI 金表上移至建模层与 compiled SQL。
- KPI 从交互量转向 Agentic 占比。

## 可带回团队的问题

- 能否量化每层语义对问数准确率的贡献？
- 语义是否进统一 catalog，还是仍在猜 Join？

## 下期观察

- Gateway OTel 能否统一问数成本与轨迹。

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
