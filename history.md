--这个文档用来存放定时的AI新闻收集

# AI×分析团队转型 · 2026-08-21

## 深挖
1. **苏格兰水务对话分析工艺** Genie 不连原始表，而用 gold 层、metric views、业务规则与基准问答集；经 Teams/Copilot/MCP 嵌入协作流，并监控采纳、质量、成本。动作：选一个高频场景建 25–50 题评测集作上线门禁。https://www.databricks.com/blog/how-scottish-water-made-its-capital-investment-data-conversational-databricks-genie

2. **Grab 机械工单 44%→30%** 五级自治下，3–5 月指标/取数/SQL 自助无人答复率明显提升；ContextIQ 把 Agent 失败反哺上下文。动作：定义机械工单占比与自助成功率基线 KPI。https://www.infoq.com/news/2026/08/grab-ai-analytics-agents/

3. **语义层+血缘双支柱** 语义层定义「收入指什么」，血缘证明「数从哪来可否信」；SQL 正确仍可能口径/源端出错。动作：先锁 revenue/churn 等争议指标，补定义-来源-聚合规则。https://www.precisely.com/blog/datagovernance/why-ai-needs-a-semantic-layer/

4. **工程就绪六维评分** 策略分难预测上生产；管道、评测、可观测、回滚、集成、权属六维才可半天核实。动作：选一用例，数据/部署/owner 三人打分，<3 分必配 remediation owner。https://saigontechnology.com/blog/ai-readiness-assessment/

## 趋势
- 分析 AI 从能问数转向可运营：评测集、监控、回滚、审批门禁成标配。

## 可带回团队的问题
- 「黄金 25–50 题」是否版本化并作为语义变更回归门禁？
- KPI 是否追踪机械工单占比与自助无人答复率？

## 下期观察
- 公营/基建是否复制「gold+metric views+Teams 嵌入」模板。
