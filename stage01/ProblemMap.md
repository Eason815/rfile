# ACL Agent 研究问题与方法路线地图

<!-- AUTO:PROBLEM_MAP:START -->
更新日期：2026-11-02。本页汇总主文分析样本中的研究问题与主要方法路线。
资料层级与筛选范围见[Stage01数据范围](README.md)。不同任务的实验结果不作直接性能排序；研究判断与方向安排见正文第05–07节。
本页仅统计主会长文，逐篇记录见[长文论文池](PaperPool-Long.md)。

## 问题索引

|ID|Research Question|主会长文|逐篇问题记录|方法标签数（未归并）|
|---|---|---|---|---|
|ACL-Q001|Agent如何规划并执行工具调用或信息获取步骤，以完成复杂任务？|10|10|10|
|ACL-Q002|多Agent如何通过角色分工、路由与协作机制，提高共同任务完成质量？|15|15|15|
|ACL-Q003|Agent如何把开放式答案探索与可验证的任务求解衔接起来？|2|2|2|
|ACL-Q004|如何从带噪声的交互轨迹中构造可靠训练信号，提高Agent的行动质量？|6|6|6|
|ACL-Q005|Agent如何组织、更新并正确利用交互记忆，支持后续决策与行动？|10|10|10|
|ACL-Q006|如何可靠评测Agent的任务完成质量、交互表现及失败原因？|15|15|15|
|ACL-Q007|如何识别并防御Agent交互、工具与信息链中的安全风险？|6|6|6|
|ACL-Q008|如何利用奖励、反馈和强化学习改善Agent的多步决策策略？|17|17|17|
|ACL-Q009|如何在预算约束下提高Agent推理、上下文管理与执行效率？|6|6|6|
|ACL-Q010|如何使Agent基于检索证据可靠判断、处理冲突并减少幻觉？|2|2|2|
|ACL-Q011|如何提高Agent在代码、GUI与具身环境中的任务执行能力？|1|1|1|
|ACL-Q012|Agent如何通过对话、个性化与社会交互更好地理解并协助用户？|5|5|5|

## 重点问题的方法路线初步对照

以下对照说明各路线处理的问题与验证条件，作为后续讨论的证据材料。核心发现的讨论工作稿见[Key Findings证据卡](KeyFindings-Worksheet.md)。

### ACL-Q001｜Agent如何规划并执行工具调用或信息获取步骤，以完成复杂任务？

先区分工具接口与规划、触发信息获取的时机，以及将任务卸载到可执行表示的路线。

|方法路线|对应记录与资料层级|机制与问题的关系|
|---|---|---|
|工具接口与分层执行|[P001 · OctoTools: A Multi-Agent Framework with Extensible Tools for Complex Reasoning](https://aclanthology.org/2026.acl-long.1/)（官方摘要已核读；Core）|工具卡明确接口，规划器组织高低层步骤，执行器承接动作。|
|任务内迭代阅读|[P007 · IntrAgent: An LLM Agent for Content-Grounded Information Retrieval through Literature Review](https://aclanthology.org/2026.acl-long.29/)（官方摘要已核读；Related）|结构知识辅助章节排序，按任务迭代提取细节并综合答案。|

待核查的比较条件：分别检查规划质量、工具接口约束、外部调用预算、编译或检索失败的处理方式；不同任务的准确率和成本数字不能直接横比。
问题边界：模型内部推理和普通单轮RAG不是同一问题；Edge工具组件仅提供潜在支撑，须核实完整Agent执行环节。

### ACL-Q004｜如何从带噪声的交互轨迹中构造可靠训练信号，提高Agent的行动质量？

比较可靠训练信号来自逐步过滤、失败动作的反事实核验，还是诊断驱动的定向合成。

|方法路线|对应记录与资料层级|机制与问题的关系|
|---|---|---|
|合成轨迹与步骤过滤|[P005 · WebSTAR: Scalable Data Synthesis for Computer Use Agents with Step-Level Filtering](https://aclanthology.org/2026.acl-long.21/)（官方摘要已核读；Core）|构造交互轨迹，过滤步骤并蒸馏步骤奖励；重点是合成监督的质量。|
|文本隐含经验与模拟环境合成|[P1449 · Unlocking Implicit Experience: Synthesizing Tool-Use Trajectories from Text](https://aclanthology.org/2026.acl-long.452/)（官方摘要已核读；Related）；[P1459 · Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards](https://aclanthology.org/2026.acl-long.570/)（官方摘要已核读；Related）|GEM从文本提取并ground多轮工具轨迹，再蒸馏生成器；SYNTHAGENT联合合成任务、工具生态、模拟用户与rubric奖励。前者重轨迹来源，后者重可训练环境。|

待核查的比较条件：核查数据规模、教师成本、关键动作成功的验证方法、错误标签噪声，以及提升是否迁移到新环境。
问题边界：Agent参与数据生成与被训练对象本身是Agent需要区分；普通预训练语料处理只能作为Edge支撑，不能当作交互行动质量证据。

### ACL-Q005｜Agent如何组织、更新并正确利用交互记忆，支持后续决策与行动？

区分任务内相关上下文、跨任务解法经验、跨会话事件记忆和记忆到行动的落地；它们并非同一种记忆能力。

|方法路线|对应记录与资料层级|机制与问题的关系|
|---|---|---|
|查询对齐的记忆路径生长|[P1400 · MemSearch-o1: Empowering Large Language Models with Reasoning-Aligned Memory Growth in Agentic Search](https://aclanthology.org/2026.acl-long.41/)（官方摘要已核读；Related）|从查询种子生长片段，贡献函数回溯精炼，再恢复连通路径。|
|阶段简报与干扰精炼|[P1408 · COMPASS: Enhancing Agent Long-Horizon Reasoning with Evolving Context](https://aclanthology.org/2026.acl-long.152/)（官方摘要已核读；Related）；[P1409 · Mitigating Context Interference for Reliable and Efficient Search Agents](https://aclanthology.org/2026.acl-long.160/)（官方摘要已核读；Related）|COMPASS分离执行、监督和上下文管理；精炼器工作分析检索干扰并把上下文精炼纳入训练。|
|历史解法的结构化经验|[P1420 · Dual-Cluster Memory Agent: Resolving Multi-Paradigm Ambiguity in Optimization Problem Solving](https://aclanthology.org/2026.acl-long.266/)（官方摘要已核读；Related）|按建模与编码聚类，把历史解法归纳为Approach/Checklist/Pitfall以指导修错与路线切换。|
|事件框架与来源回溯|[P1422 · Structured Episodic Event Memory](https://aclanthology.org/2026.acl-long.277/)（官方摘要已核读；Related）|以事实图和情节层组织交互事件，通过来源指针重建叙事上下文。|
|主动记忆应用的行为评测|[P1434 · Mem2ActBench: A Benchmark for Evaluating Long-Term Memory Utilization in Task-Oriented Autonomous Agents](https://aclanthology.org/2026.acl-long.370/)（官方摘要已核读；Core）|检查Agent能否在没有显式提醒时利用历史记忆选择工具并填充参数；这是评测路线，不是新的记忆算法。|
|学习记忆操作与检索后推理|[P1464 · Memory-R1: Enhancing Large Language Model Agents to Manage and Utilize Memories via Reinforcement Learning](https://aclanthology.org/2026.acl-long.583/)（官方摘要已核读；Related）；[P1456 · Chain-of-Memory: Lightweight Memory Construction with Dynamic Evolution for LLM Agents](https://aclanthology.org/2026.acl-long.534/)（官方摘要已核读；Related）|Memory-R1以RL学习增删改和回答选择；CoM强调轻量构建后把片段组织为动态推断链。对话QA实验与真实行动证据单列。|

待核查的比较条件：分别核对记忆生命周期、写入/压缩/召回控制、错误传播及实际工具行为。MemSearch等任务内搜索、SEEM的对话记忆基准与Mem2ActBench的动作参数任务不能直接横比；持久记忆和临时工作上下文单列。
问题边界：方法论文与基准论文区分。纯KV缓存和静态参数记忆只作Q009/Q010组件；“记得事实”不等于“用记忆完成行动”。

### ACL-Q006｜如何可靠评测Agent的任务完成质量、交互表现及失败原因？

把Agent评价拆成不同能力轴，避免仅以一个成功率覆盖安全副作用、约束遵循、用户交互和推理诊断。

|方法路线|对应记录与资料层级|机制与问题的关系|
|---|---|---|
|电商功能覆盖与副作用|[P1402 · A Functionality-Grounded Benchmark for Evaluating Web Agents in E-commerce Domains](https://aclanthology.org/2026.acl-long.68/)（官方摘要已核读；Related）|从页面功能构建查询，同时评价完成请求和账户状态的非预期改动。|
|真实工具工作流|[P1415 · MedMCP-Calc: Benchmarking LLMs for Realistic Medical Calculator Scenarios via MCP Integration](https://aclanthology.org/2026.acl-long.221/)（官方摘要已核读；Related）；[P1423 · MobileWorld: Benchmarking Autonomous Mobile Agents in Agent-User Interactive and MCP-Augmented Environments](https://aclanthology.org/2026.acl-long.278/)（官方摘要已核读；Related）；[P1426 · MAS-Bench: A Unified Benchmark for Shortcut-Augmented Hybrid Mobile GUI Agents](https://aclanthology.org/2026.acl-long.316/)（官方摘要已核读；Related）|医疗计算检查数据获取和计算器使用；移动端分别覆盖用户/MCP交互与GUI/快捷方式混合执行。|
|持续指令及全局约束|[P1421 · OctoBench: Benchmarking Scaffold-Aware Instruction Following in Repository-Grounded Agentic Coding](https://aclanthology.org/2026.acl-long.269/)（官方摘要已核读；Related）；[P1430 · DeepPlanning: Benchmarking Long-Horizon Agentic Planning with Verifiable Constraints](https://aclanthology.org/2026.acl-long.335/)（官方摘要已核读；Related）|编码脚手架检查任务成功之外的规则遵循；长程规划检查主动信息获取和局部/全局预算约束。|
|解释与推理的白盒诊断|[P1425 · TriEx: A Game-based Tri-View Framework for Explaining Internal Reasoning in Multi-Agent LLMs](https://aclanthology.org/2026.acl-long.292/)（官方摘要已核读；Related）；[P1438 · From Laboratory to Real-World Applications: Benchmarking Agentic Code Reasoning at the Repository Level](https://aclanthology.org/2026.acl-long.399/)（官方摘要已核读；Related）|TriEx对齐解释、信念与行动；RepoReason用执行真值和程序切片诊断读取、模拟及跨文件整合。|

待核查的比较条件：核对状态真值能否自动验证、任务分布和环境重置、指标粒度、轨迹可观测性、工具权限与调用预算。基准的不同能力轴单独报告，不合并成未经验证的统一排名。
问题边界：评测对象与方法性能区分；多Agent用于漏洞检测不是Agent自身安全评测；模拟医疗计算、游戏和移动应用结果保留场景边界。

### ACL-Q009｜如何在预算约束下提高Agent推理、上下文管理与执行效率？

先选资源单位：墙钟时间、历史token/内存、预填充成本或训练显存，再看能力损失如何衡量。

|方法路线|对应记录与资料层级|机制与问题的关系|
|---|---|---|
|墙钟预算感知|[P1413 · Timely Machine: Awareness of Time Makes Test-Time Scaling Agentic](https://aclanthology.org/2026.acl-long.211/)（官方摘要已核读；Related）|把工具等待纳入时间预算，以延迟变化测试并训练时间规划。|
|交互历史的光学压缩|[P1418 · AgentOCR: Reimagining Agent History via Optical Self-Compression](https://aclanthology.org/2026.acl-long.230/)（官方摘要已核读；Related）|图像化历史、分段缓存和自选压缩率共同控制Agent轨迹成本。|
|多Agent评价器的缓存风险|[P1428 · When KV Cache Reuse Fails in Multi-Agent Systems: Cross-Candidate Interaction is Crucial for LLM Judges](https://aclanthology.org/2026.acl-long.327/)（官方摘要已核读；Related）|用JCR检查KV复用是否改变评价器候选选择，不能仅检查最终准确率。|
|查询条件工作流调度|[P1463 · LLM-as-Scheduler: Agentic Workflow Dynamic Scheduling](https://aclanthology.org/2026.acl-long.581/)（官方摘要已核读；Related）|LAS以轻量gate和LLM调度器为查询选择适当工作流，报告成本时同时保留准确率损失。|

待核查的比较条件：统一模型、硬件、工具延迟、输入/输出规模、rollout数和任务成功约束后才能比较成本；区分训练显存、推理峰值显存和端到端耗时。
问题边界：通用推理基准收益不能直接视为Agent收益；光学历史压缩是多轮行动轨迹机制，不能与普通KV压缩混作同一实验。

### ACL-Q008｜如何利用奖励、反馈和强化学习改善Agent的多步决策策略？

区分训练环境、步骤信用分配、行为校准和随策略变化的反馈；相同“RL”标签不代表解决同一种问题。

|方法路线|对应记录与资料层级|机制与问题的关系|
|---|---|---|
|低成本多轮经验环境|[P1443 · Experience-driven Multi-turn Reinforcement Learning for GUI Agents](https://aclanthology.org/2026.acl-long.428/)（官方摘要已核读；Related）|EMPO用专家经验提供匹配动作的状态转移，Patch修补不匹配步骤，以自生成历史训练长程策略。|
|关键错误与轮级信用|[P1453 · Learning from the Irrecoverable: Error-Localized Policy Optimization for Tool-Integrated LLM Reasoning](https://aclanthology.org/2026.acl-long.504/)（官方摘要已核读；Related）；[P1457 · MatchTIR: Fine-Grained Supervision for Tool-Integrated Reasoning via Bipartite Matching](https://aclanthology.org/2026.acl-long.549/)（官方摘要已核读；Related）|ELPO用有限预算搜索第一不可恢复错误；MatchTIR匹配真值轨迹给轮级奖励。两者的可用监督和有效路径假设不同。|
|奖励密度及调用校准|[P1429 · ET-Agent: Incentivizing Effective Tool-Integrated Reasoning Agent via Behavior Calibration](https://aclanthology.org/2026.acl-long.333/)（官方摘要已核读；Related）；[P1450 · Reinforcing Agentic Search Via Reward Density Optimization](https://aclanthology.org/2026.acl-long.467/)（官方摘要已核读；Related）；[P1468 · DORA: A Dual-Objective Reinforcement Learning Framework for Effective and Efficient Multimodal Agentic Search](https://aclanthology.org/2026.acl-long.605/)（官方摘要已核读；Related）|ET-Agent校准冗余/不足调用；InfoFlow提高单位探索成本的奖励；DORA联合搜索质量、正确率和少调用。|
|策略与批评器共同演化|[P1461 · No More Stale Feedback: Co-Evolving Critics for Open-World Agent Learning](https://aclanthology.org/2026.acl-long.576/)（官方摘要已核读；Related）|ECHO同步更新策略与诊断批评器，针对策略变化后的反馈陈旧与改进饱和。|

待核查的比较条件：核对环境真实性、真值轨迹可得性、额外rollout/教师预算、奖励能否被投机，以及训练与部署历史是否一致；对照最终成功、调用效率和训练稳定性时保持环境及预算相同。
问题边界：合成数据质量主归Q004；RL用于记忆增删仍以记忆问题主归Q005；通用模型训练的Edge不能被当成Agent多轮行动证据。

### ACL-Q007｜如何识别并防御Agent交互、工具与信息链中的安全风险？

先按风险进入系统的位置区分：工具反馈中的恶意指令，与Agent自身执行动作的违规或上下文风险。

|方法路线|对应记录与资料层级|机制与问题的关系|
|---|---|---|
|工具流注入的提交前验证|[P1447 · VIGIL: Defending LLM Agents Against Tool-Stream Injection via Verify-Before-Commit](https://aclanthology.org/2026.acl-long.443/)（官方摘要已核读；Related）|VIGIL保留推测推理，但在执行提交前按意图验证；SIREN测试动态依赖工具流注入。|
|系统规则与上下文混合检测|[P1444 · OS-Sentinel: Towards Safety-Enhanced Mobile GUI Agents via Hybrid Validation in Realistic Workflows](https://aclanthology.org/2026.acl-long.431/)（官方摘要已核读；Related）|OS-Sentinel用Formal Verifier检测显式系统违规，VLM Contextual Judge处理依赖上下文的风险；MobileRisk-Live提供动态沙箱轨迹。|

待核查的比较条件：分别核对威胁模型、攻击者控制的输入、检测与阻断的时机、漏报/误报和正常任务效用。工具流攻击成功率与GUI风险检测指标不是同一量，不做横向冠军排名。
问题边界：漏洞检测、法律合规判断等业务任务不自动归作Agent自身安全；有限攻击集或风险轨迹不能证明普遍安全。

## 分析边界

本页未纳入Edge和Agent联系尚不明确的背景材料。相关资料保留原有编号，不计入本页研究问题统计。问题之间存在交叉联系时，表中标明主问题归属。
<!-- AUTO:PROBLEM_MAP:END -->

## 人工批注

