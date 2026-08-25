--这个文档用来存放定时的AI新闻收集

# AI×分析团队转型 · 2026-08-25

## 深挖

1. **PostHog：指标「提案→批准→漂移」**  
多 Agent 对同一指标各写 SQL 得不同数，因口径仅存于人脑。PostHog 规定 Agent 产出一律 `proposed`，人工批准才 canonical；改定义回退待审，上游洞察变更标 `drifted`。  
**动作**：核心指标建三态，Agent 只读 approved 且未 drift。  
https://posthog.com/blog/semantic-layer

2. **Databricks：Agentic BI 分阶委派**  
数据准备、例行报告可委派 Agent，向业务交付前须审批；单 BU 试点，先定洞察时效、工时回收、满意度、准确率再扩面。  
**动作**：选财务等清晰场景做 4 周试点，写清可委派/须人工清单。  
https://www.databricks.com/blog/what-is-agentic-bi

3. **AI 主导数据交付六步**  
交付从建造变监督：框定问题→AI 规划→生成管道/指标/测试→自动+人工校验→ governed 发布→持续学习；工程变监督者，治理变持续监控。  
**动作**：需求单加「AI 生成物验收项」（口径、血缘、测试）。  
https://medium.com/@anandad12/post-2-operating-model-and-project-lifecycle-for-ai-led-data-delivery-c0413e1eb4ba

4. **Cloudflare OS：Gatekeeper 零信任 MCP**  
分析 Agent 常因 MCP 过宽触敏感列。Gatekeeper 细粒度授权、脱敏、限速，破坏性操作须人工批，默认零权限。  
**动作**：盘点 Agent 连接，改按需 capability + 写操作审批。  
https://www.infoq.com/news/2026/08/cloudflare-os-ai-platform-secure/

5. **BI 分析师应「拥有」语义层**  
Agent 以机器速度产出答案后，指标治理缺口被放大；Refonte 认为 BI 分析师应主导 revenue/churn 等口径定义、认证与 MCP 暴露，而非把语义层留给工程侧事后补建。  
**动作**：指定 2–3 名 senior 分析师为指标 Owner，每周审 proposed 定义。  
https://www.refontelearning.com/blog/semantic-layer-for-ai-agents

## 趋势

- 治理重心从「查对 SQL」上移至指标定义生命周期与审批流。
- 内部分析自助化走向平台层统一身份/权限，而非各部门各自接模型。

## 可带回团队的问题

- 核心指标有无 proposed/approved/drifted 状态，还是 Agent 每次自由写 SQL？
- 分析团队在 hub-spoke 里算 hub（平台/治理）还是 spoke（用例/验收）？

## 下期观察

- Cube 等 Agentic Analytics Loops 是否成可运营标准。
