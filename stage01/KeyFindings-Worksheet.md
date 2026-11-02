<!-- AUTO:FINDINGS_CARDS:START -->
# Key Findings｜证据与研究判断

三张证据卡已形成F01–F03。事实、方法对照、研究判断及证据边界分别记录。

## 资料范围

九篇论文均已在此前核读原始摘要；本轮只复用缓存，不新增原始摘要核读、精读、Open Problems或论文池计数。

正式报告见[Stage 01 · Broad Scan](README.md)。

<a id="k01"></a>

## K01｜记忆组织、记忆操作与行动应用

对应问题：ACL-Q005；对应发现：F01。

### 研究问题

组织好历史、学会记忆操作与正确使用记忆完成工具动作，是否需要分别验证？

### Fact｜作者摘要所报告的事实

- SEEM摘要将碎片交互的关系与叙事连贯性列为组织问题；Memory-R1摘要将记忆管理与选择使用设为可学习策略。

- Mem2ActBench作者报告，七种记忆框架在主动利用历史完成工具参数落地方面仍有不足；该观察限于其合成任务。

### Evidence｜机制与验证目标

|论文|关键机制|验证目标或场景|路线区别|
|---|---|---|---|
|[P1422 · Structured Episodic Event Memory](https://aclanthology.org/2026.acl-long.277/)|SEEM以事实图层、情节层及来源指针组织事件，通过反向来源扩展重建上下文。|LoCoMo、LongMemEval；作者报告优于基线。|重点验证记忆组织与叙事推理。|
|[P1464 · Memory-R1: Enhancing Large Language Model Agents to Manage and Utilize Memories via Reinforcement Learning](https://aclanthology.org/2026.acl-long.583/)|Memory-R1分别训练记忆增删改等操作及答案Agent的筛选推理，使用结果奖励。|152组训练问答，三个对话记忆基准。|重点是操作和使用策略的学习。|
|[P1434 · Mem2ActBench: A Benchmark for Evaluating Long-Term Memory Utilization in Task-Oriented Autonomous Agents](https://aclanthology.org/2026.acl-long.370/)|Mem2ActBench从持续交互记忆链反向生成工具任务，检查工具选择与参数落地。|400个工具任务、七种记忆框架；有人工依赖性检查。|是行动使用评测，不是记忆算法。|

资料依据为已保存的官方摘要；本页未增加正文实验或消融结论。

### 反向证据与替代解释

- 问答表现与工具行动表现来自不同任务，不能用三篇的结果直接排列方法优劣。

- 参数错误还可能来自工具理解或任务推理，不能仅凭最终失败归因于记忆检索。

### Uncertainty｜证据边界

- 尚未核查相同预算、记忆依赖性构造与正文消融，不能确定组织、检索和行动推理各自的贡献。

### 进一步研究的问题

1. 应优先聚焦跨会话偏好到工具参数的落地，还是更一般的长期经验利用；哪一种问题边界更适合后续深入？

2. 哪些可比条件及反向证据会改变上述研究判断？

### 研究判断

记忆质量不能仅由事实回忆或问答分数代表，还需要检验历史是否在正确时机转化为正确行动。后续更值得聚焦记忆利用链中的失效位置，区分组织、检索、工具理解与参数落地错误。

### 下一阶段安排

Continue：进入Stage 02，优先研究历史信息到工具参数的转化与错误归因，先明确评测协议，再选择记忆机制。

<a id="k02"></a>

## K02｜多步策略学习的信号来源与更新方式

对应问题：ACL-Q008；对应发现：F02。

### 研究问题

细化训练信号的收益，主要来自更准确的信用分配、更强监督，还是更适应当前策略的反馈？

### Fact｜作者摘要所报告的事实

- ELPO与MatchTIR摘要均认为轨迹级结果奖励难以区分有效步骤和错误步骤，但构造局部信号的依据不同。

- ECHO作者将策略变化后批评器反馈过时作为问题，报告共同更新策略和批评器可改善其开放世界任务训练。

### Evidence｜机制与验证目标

|论文|关键机制|验证目标或场景|路线区别|
|---|---|---|---|
|[P1453 · Learning from the Irrecoverable: Error-Localized Policy Optimization for Tool-Integrated LLM Reasoning](https://aclanthology.org/2026.acl-long.504/)|ELPO以固定预算的二分搜索rollout树定位首个不可恢复错误，再进行层次优势归因与局部裁剪。|数学、科学问答和代码执行；摘要称采样预算可比。|通过续跑结果定位关键错误。|
|[P1457 · MatchTIR: Fine-Grained Supervision for Tool-Integrated Reasoning via Bipartite Matching](https://aclanthology.org/2026.acl-long.549/)|MatchTIR将预测与真值轨迹做二分图匹配，产生轮级奖励并结合轨迹级优势。|三个基准；摘要未列出名称。|依靠真值轨迹提供细粒度监督。|
|[P1461 · No More Stale Feedback: Co-Evolving Critics for Open-World Agent Learning](https://aclanthology.org/2026.acl-long.576/)|ECHO以多诊断后修订、饱和感知增益整形及双轨GRPO，共同更新策略与批评器。|开放世界长程任务；摘要报告训练更稳定、成功率提高。|使反馈随策略变化而更新。|

资料依据为已保存的官方摘要；本页未增加正文实验或消融结论。

### 反向证据与替代解释

- 收益也可能受额外续跑、真值轨迹质量或诊断生成预算影响，不能全部归因于奖励更细。

- 任务和训练条件不同，当前材料不支持三种路线的横向优劣排序。

### Uncertainty｜证据边界

- 尚未核对总训练成本、关键错误判定及多解轨迹覆盖；摘要不能分离每个组件的作用。

### 进一步研究的问题

1. 后续应优先研究无真值轨迹的低成本信用信号，还是先在固定任务上厘清现有监督路线的收益来源？

2. 哪些可比条件及反向证据会改变上述研究判断？

### 研究判断

“奖励更细”不足以解释这些方法的差异，信号依据与更新方式决定了它们解决哪一类训练困难。比较时应同时记录真值依赖、额外续跑和反馈生成成本，再判断信用分配本身的贡献。

### 下一阶段安排

Observe：保持观察，先对照局部信用信号的可靠性和获取成本；在训练条件与预算边界明确后，再决定是否作为独立主线。

<a id="k03"></a>

## K03｜任务完成之外的约束、副作用与成本

对应问题：ACL-Q006；对应发现：F03。

### 研究问题

任务成功率之外，还需分别衡量哪些维度，才能判断Agent的执行是否可接受？

### Fact｜作者摘要所报告的事实

- Amazon-Bench摘要同时评价电商任务性能与安全；OctoBench将完成编码任务和遵守脚手架规则分开评分。

- CostBench作者报告，工具Agent在成本最优规划及动态变化下仍存在不足；这针对旅行工具任务，并非一般部署结论。

### Evidence｜机制与验证目标

|论文|关键机制|验证目标或场景|路线区别|
|---|---|---|---|
|[P1402 · A Functionality-Grounded Benchmark for Evaluating Web Agents in E-commerce Domains](https://aclanthology.org/2026.acl-long.68/)|Amazon-Bench依据网页功能生成任务，同时检查任务结果与非预期账户改动。|地址、愿望清单等电商功能；作者报告复杂任务与安全困难。|关注执行产生的负面副作用。|
|[P1421 · OctoBench: Benchmarking Scaffold-Aware Instruction Following in Repository-Grounded Agentic Coding](https://aclanthology.org/2026.acl-long.269/)|OctoBench记录完整轨迹，以客观检查项区分仓库任务解答与规则遵循。|34个环境、217个任务、7098项检查；八个模型。|关注全过程指令合规。|
|[P1465 · CostBench: Evaluating Multi-Turn Cost-Optimal Planning and Adaptation in Dynamic Environments for LLM Tool-Use Agents](https://aclanthology.org/2026.acl-long.584/)|CostBench设定原子和组合工具成本，引入四类动态阻断，检查成本最优与重规划。|旅行规划；比较静态与动态条件。|关注资源最优性与环境适应。|

资料依据为已保存的官方摘要；本页未增加正文实验或消融结论。

### 反向证据与替代解释

- 多设指标不自动意味着评分可靠；检查项、成本设定与任务分布也可能影响结论。

- 三篇度量不同对象，不能把它们相加为统一总分或据此排名Agent。

### Uncertainty｜证据边界

- 副作用判据、检查项完备性、最优解计算和用户偏好一致性尚待正文核查。

### 进一步研究的问题

1. 在选定Agent任务中，哪些违规必须判为失败，哪些成本可以与成功率权衡；该协议是否足以作为独立研究贡献？

2. 哪些可比条件及反向证据会改变上述研究判断？

### 研究判断

Agent“完成了任务”与“执行可以接受”需要分别判断。后续评测应保留成功、约束违规、副作用和成本的独立结果，并依据任务需求区分硬约束与可权衡目标，避免一个总分掩盖重要失败。

### 下一阶段安排

Continue：进入Stage 02作为记忆到行动研究的评测支撑，先明确错误类型与约束判据；暂不单独扩展为通用大规模基准。
<!-- AUTO:FINDINGS_CARDS:END -->

## 研究记录

以下区域保留补充研究记录与批注。

### K01

已形成F01；研究判断与方向建议见正文及上方证据卡。

### K02

已形成F02；研究判断与方向建议见正文及上方证据卡。

### K03

已形成F03；研究判断与方向建议见正文及上方证据卡。

