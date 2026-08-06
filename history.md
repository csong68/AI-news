--这个文档用来存放定时的AI新闻收集

---

# AI×分析团队转型 · 2026-08-06

## 深挖

1. **Agent 优先数据栈（LangChain）**  
LangChain 数据团队不再逐条答疑，而是维护 dbt、语义模型、工作区指南，并用对话可观测性找上下文缺口。  
**动作**：选一个高频问数主题，把口径与 Join 规则写成 Agent 可读指南并每周复盘日志。  
https://www.langchain.com/blog/agent-data-stack

2. **完美 SQL 仍可能说谎（Thomson Reuters）**  
73% 时间分析存在跨表时间过滤不一致；语法通过的查询仍可能漏业务过滤。  
**动作**：为 Agent 输出加「时间窗/转化口径/Join 键」业务校验清单，抽检追踪日志。  
https://medium.com/tr-labs-ml-engineering-blog/is-your-ai-agent-lying-with-perfect-sql-3a6a7d69bccf

3. **测试驱动分析（dbt）**  
把测试嵌入 PR/CI，以 70–80% 模型覆盖率与「问题检出耗时」衡量质量，而非堆测试数。  
**动作**：为核心指标模型补 primary key 测试，PR 失败即阻断合并。  
https://www.getdbt.com/blog/test-driven-analytics-workflow

4. **SQL Agent YAML 合约（Google）**  
MCP Toolbox 用 YAML 白名单约束 Agent 可执行 SQL，架构师与 DBA 共定边界，默认禁未授权写操作。  
**动作**：试点 5–10 条参数化只读模板，写操作单独工具且需审批。  
https://medium.com/google-cloud/from-chaos-to-control-securing-ai-agent-database-connections-with-google-mcp-toolbox-and-google-db9e91251ecd

5. **结构化工作流先行（Microsoft Fabric）**  
数据质量监控、画像、流异常检测等可度量任务，是 Agent 落地置信度最高的入口。  
**动作**：选一条现有 DQ 告警，试点「检测→解释→建议」半自动流程。  
https://www.microsoft.com/en-us/microsoft-fabric/blog/2026/06/29/why-data-teams-are-emerging-as-leaders-in-ai-agent-adoption/

## 趋势
- 团队考核从交付量转向上下文资产与 Agent 可观测性。
- 语义层/指标标准化是 Agent 复用前提，非锦上添花。

## 可带回团队的问题
- 「答对」标准如何定：语法、口径还是决策可用？
- 自由 SQL 与参数化模板应在哪一层切换？

## 下期观察
- 对话日志自动转 dbt/语义层 PR 的公开实践是否增多。
