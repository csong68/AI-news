--这个文档用来存放定时的AI新闻收集

---

# AI×分析团队转型 · 2026-08-06

## 深挖

1. **人机四层协作**（ODSC）：自动化做重复执行，增强做初稿，判断做解读，问责做签批；幻觉需流程化复核而非偶发故障。**动作**：标注分析链路四层，高影响输出强制人工确认。https://odsc.medium.com/managing-human-ai-workflows-the-operating-model-most-teams-are-missing-ac344e193cd9

2. **12域Agent化地图**（Joshua Data）：沿管道/质量/消费/组织四轴，将团队判断编码为Skills与Agent共享，影响不再绑人头。**动作**：选取数+文档+质检单域试点，先沉淀可复用Skill。https://joshua-data.medium.com/12-areas-to-adopt-agentic-ai-en-6ecd93670683

3. **编排-工作者模式**（90天实践）：编排者只管任务图，Worker专责SQL/解读/汇总；数据质量巡检ROI最高。**动作**：部署只读Agent做晨间异常扫描，人工仅处理告警。https://medium.com/ai-analytics-diaries/i-replaced-half-my-analytics-workflow-with-ai-agents-for-90-days-d65908904222

4. **ISO 5259-5治理框架**：2025年发布，为分析/ML提供董事会级数据质量 oversight，明确战略对齐与问责。**动作**：对照标准梳理RACI与升级机制缺口。https://www.iso.org/standard/84150.html

5. **语义层克制Agent**（Thoughtworks Radar）：裸text-to-SQL易错，业务规则须进语义层；建议单域起步。**动作**：为一个核心指标域建语义模型后再开放Agent查询。https://www.thoughtworks.com/radar/techniques/semantic-layer

## 趋势

- OSI v1.0多厂商共建，语义定义可跨BI与Agent复用。
- 人机Hybrid已是交付常态，瓶颈在运营模型而非工具选型。

## 可带回团队的问题

- 哪些分析环节仍是个体提效，未做端到端流程重设计？
- Agent能否直连原始表，还是必须走语义层？

## 下期观察

- dbt Wizard「验证再发布」工作流能否成为团队标准门禁
