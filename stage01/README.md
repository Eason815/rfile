# Stage 01 · Broad Scan｜ACL 2026 Agent

|Stage|01 · Broad Scan（广泛扫描）|
|---|---|
|Question|2026 年有哪些研究问题正在被集中研究？|
|Output|数据范围 / 论文池 / 研究问题 / 趋势证据 / 核心发现 / Stage 02 候选|
|Owner|ACL Agent方向调研负责人|
|Updated|2026-11-02|

# 00｜Overview

## 本轮覆盖

- **会议 / 数据范围：**ACL 2026主会长文；Agent相关研究
- **当前公开记录数：**2222篇（官方目录快照）
- **实际扫描：**1550篇逐项标题初筛；目录标题覆盖2222篇（含672篇来源映射）
- **纳入分析：**95篇重点问题复核样本；另保留754篇宽口径长文收纳记录
- **形成研究问题：**12个研究问题
- **数据完整性：**基本完整（固定目录快照标题覆盖完成，分析结论基于筛选样本）

## 本轮最重要的3个发现

1. **F01：记忆的价值需要沿组织、操作到行动执行分别验证。**
2. **F02：细粒度训练信号需要区分信用定位、监督来源与反馈时效。**
3. **F03：任务完成率之外，需要分别评价过程约束、副作用与成本。**

## Stage 02重点安排

1. **Continue｜记忆到行动：**研究历史信息怎样转化为正确工具选择与参数，并区分失效环节。
2. **Continue｜多维评测：**作为记忆研究的验证支撑，分别报告成功、约束、副作用与成本。
3. **Observe｜信用信号训练：**先比较监督来源与获取成本，再确定训练路线的投入范围。

## 组会研究问题

**[Question]** 应先选择哪类历史依赖工具任务，以及怎样界定记忆贡献、行动错误和不可违反的约束？

# 01｜Data Scope

## 数据范围

|Item|Record|
|---|---|
|会议 / 数据集|ACL 2026主会长文；Agent|
|主要数据源|[官方论文集](https://aclanthology.org/volumes/2026.acl-long/) / [Paper Notes](https://papernotes.org/ACL2026/)|
|获取日期|2026-10-28（官方目录）|
|当前公开记录数|2222篇（目录快照）|
|实际扫描数量|1550篇逐项标题初筛；标题覆盖2222篇（含672篇来源映射）|
|纳入分析数量|95篇重点问题复核样本；广泛收纳754篇另行保留|
|扫描方式|标题初筛、来源映射及简介／解读整理；部分官方摘要核读|
|最近更新|2026-11-02|

## Scope

**本次覆盖：**对ACL 2026主会长文进行标题初筛与资料整理，广泛收纳754篇直接相关、组件支撑及擦边材料。研究问题表采用95篇复核样本，其中68篇依据官方摘要、27篇依据第三方简介／解读。负责人已阅读本轮整理材料。

**排除范围：**其他轨道与短文不计入本页统计。Edge和背景材料保留原记录，不进入问题占比分母。

## Data Limitation

- **目录边界：**采用2026-10-28保存的主会长文目录快照，2222篇标题均有检查或来源映射记录；不据此声明实时目录无遗漏。
- **Track：**仅统计主会长文。
- **资料依据：**官方摘要与第三方解读分别记录；本报告不新增缺少证据位置的正文实验结论。负责人阅读声明不改变AI摘要核读、精读或PDF下载计数。
- **跨年比较：**2025补充6篇方法参照，没有形成同口径数量样本，不计算跨年占比变化或独立团队数量。

本页数量与占比描述所选论文样本，不代表ACL总体方向分布。

# 02｜Paper Pool

## 论文池

下表保留95篇复核样本及原P编号。完整附表见[长文论文池](PaperPool-Long.md)；[全部收纳记录](PaperPool-All.md)保留更广泛的材料和来源，不混入本页长文统计。

|ID|Paper|Research Question|Method|纳入原因|Role|Link|
|---|---|---|---|---|---|---|
|P001|OctoTools: A Multi-Agent Framework with Extensible Tools for Complex Reasoning|ACL-Q001｜如何以可扩展工具集和分层规划执行机制，使Agent完成跨领域复杂推理任务？|标准化工具卡＋高低层规划器＋工具执行器|直接设计Agent工具扩展、计划生成与行动执行的衔接机制。|Core|[论文](https://aclanthology.org/2026.acl-long.1/)|
|P002|No Reader Left Behind: Multi-Agent Summaries Everyone Can Understand|ACL-Q002｜如何协调模拟读者与领域专家的迭代反馈，生成不同理解能力读者都能读懂且忠实于原文的摘要？|读者角色模拟＋模板规划＋反馈迭代＋专家修订|共同摘要由不同读者Agent和专家角色协同修订，直接涉及多Agent角色分工。|Related|[论文](https://aclanthology.org/2026.acl-long.2/)|
|P003|Discover and Prove: An Open-source Agentic Framework for Hard Mode Automated Theorem Proving in Lean 4|ACL-Q003｜在题目不提供最终答案的形式定理证明中，Agent如何先发现答案再构造可由Lean验证的证明？|自然语言推理与自反思发现答案，再改写命题交给形式证明器|明确研究发现答案和形式证明之间的衔接，并用Agent框架连接两个阶段。|Core|[论文](https://aclanthology.org/2026.acl-long.3/)|
|P004|PosterForest: Hierarchical Multi-Agent Collaboration for Scientific Poster Generation|ACL-Q002｜如何让内容Agent与布局Agent利用文档层次结构共同优化科学海报的语义组织和视觉布局？|Poster Tree中间表示＋内容/布局Agent分工＋层次递归修订|围绕同一海报产物协调内容与布局Agent，直接研究协作式生成流程。|Core|[论文](https://aclanthology.org/2026.acl-long.15/)|
|P005|WebSTAR: Scalable Data Synthesis for Computer Use Agents with Step-Level Filtering|ACL-Q004｜如何从强计算机操作Agent产生的噪声轨迹中筛出可靠步骤，构造可规模化的动作监督与步骤评价信号？|逐步动作过滤＋推理增强轨迹合成＋步骤评分模型蒸馏|直接处理GUI Agent训练轨迹中的错误动作及步骤标签质量。|Core|[论文](https://aclanthology.org/2026.acl-long.21/)|
|P006|How Memory Management Impacts LLM Agents: An Empirical Study of Experience-Following Behavior|ACL-Q005｜Agent记忆的添加与删除如何影响经验跟随、错误传播及后续任务表现，怎样识别值得保留的经验？|控制记忆增删条件，分析经验跟随与错误传播，利用后续任务评价形成记忆质量标签|直接研究过去执行经验如何影响Agent未来行为和记忆管理。|Core|[论文](https://aclanthology.org/2026.acl-long.27/)|
|P007|IntrAgent: An LLM Agent for Content-Grounded Information Retrieval through Literature Review|ACL-Q001｜Agent如何先定位相关论文章节，再迭代提取和综合细节，以回答严格依托给定文献内容的研究问题？|结构知识辅助章节排序＋迭代阅读细节提取与综合|直接将文献检索Agent的信息获取过程分解为章节选择和迭代行动。|Related|[论文](https://aclanthology.org/2026.acl-long.29/)|
|P008|AgentRouter: A Knowledge-Graph-Guided LLM Router for Collaborative Multi-Agent Question Answering|ACL-Q002｜如何利用问题、上下文实体和Agent之间的关系，按任务路由并聚合互补Agent的问答结果？|异构知识图谱＋性能软监督GNN路由＋输出加权聚合|直接研究任务条件下的Agent选择与结果组合。|Core|[论文](https://aclanthology.org/2026.acl-long.33/)|
|P010|AgencyBench: Benchmarking the Frontiers of Autonomous Agents in 1M-Token Real-World Contexts|ACL-Q006｜如何在包含长上下文、连续子任务与用户反馈的真实工作场景中自动评测自主Agent的产物完成质量？|能力—场景—任务分层基准＋用户模拟反馈＋隔离Docker执行＋规则与LLM评分|直接构造自主Agent长程任务评测环境、执行过程和评分协议。|Related|[论文](https://aclanthology.org/2026.acl-long.337/)|
|P015|Benchmarking Web Agent Safety under E-commerce Deceptive Interfaces|ACL-Q007｜电商网页中的可控欺骗界面会怎样改变Web Agent的行动、安全违规和任务完成表现？|在VisualWebArena按任务状态注入参数化欺骗UI，比较任务完成度与安全违规率|直接操纵Agent交互界面的欺骗风险并测量其行动后果。|Related|[论文](https://aclanthology.org/2026.acl-long.1009/)|
|P016|ChartAgent: A Multimodal Agent for Visually Grounded Reasoning in Complex Chart Question Answering|ACL-Q001｜面对缺少数值标注的图表，Agent如何通过视觉工具操作和中间结果自校验获取精确读数并完成问答？|图表元数据路由＋ReAct视觉工具循环＋中间可视化自校验与失败回退|直接把图表问答变为Agent选择工具、观察可视化和调整行动的循环。|Related|[论文](https://aclanthology.org/2026.acl-long.843/)|
|P018|CODESTRUCT: Code Agents over Structured Action Spaces|ACL-Q011｜代码Agent能否通过AST中命名程序实体的结构化读写动作，减少文本定位与编辑错误并提高仓库任务完成能力？|AST仓库表示＋实体选择器readCode/editCode工具＋编辑后语法校验|直接改变代码Agent观察和编辑环境的动作原语。|Related|[论文](https://aclanthology.org/2026.acl-long.607/)|
|P019|CoEvolve: Training LLM Agents via Agent-Data Mutual Evolution|ACL-Q004｜如何根据Agent当前遗忘、不稳定和探索稀缺的行为弱点，合成环境可验证的新任务并动态调整训练数据分布？|轨迹弱点信号提取＋条件化环境再探索＋任务合成验证＋训练数据迭代更新|直接围绕Agent交互轨迹构造针对性的训练任务和监督分布。|Related|[论文](https://aclanthology.org/2026.acl-long.1055/)|
|P021|Do LLM Agents Mirror Socio-Cognitive Effects in Power-Asymmetric Conversations?|ACL-Q006｜怎样系统测量职业权力不对称对话中Agent的语言协调、权威说服与有害服从，并检验这些效应的稳定性和可控性？|高低权力角色与persona配对＋多轮模拟对话＋语言及任务结果指标＋控制提示比较|直接评测Agent在多轮社会交互中的行为及失败风险。|Related|[论文](https://aclanthology.org/2026.acl-long.2202/)|
|P024|Don’t Click That: Teaching Web Agents to Resist Deceptive Interfaces|ACL-Q007｜Web Agent如何在点击前识别并抵抗欺骗性界面，同时避免过度拒绝合法操作，并从失败经验中改进防御？|不对称惩罚的混合奖励训练点击评估器＋失败经验摘要＋合法点击门控|直接在Agent点击执行前进行欺骗风险审核和安全行为干预。|Related|[论文](https://aclanthology.org/2026.acl-long.310/)|
|P035|HAG: Hierarchical Demographic Tree-based Agent Generation for Topic-Adaptive Simulation|ACL-Q012｜如何生成随主题变化、同时匹配宏观人口分布与微观属性一致性的Agent群体，以支持可信的社会模拟？|主题自适应人口分布树＋真实调查数据检索填充＋路径约束persona增强|直接为社会模拟构造Agent群体和用户属性模型。|Related|[论文](https://aclanthology.org/2026.acl-long.1187/)|
|P036|HeLa-Mem: Hebbian Learning and Associative Memory for LLM Agents|ACL-Q005｜Agent如何从长期对话中建立可随共激活更新的联想记忆，并结合语义巩固和扩散检索回答后续查询？|Hebbian动态图情景记忆＋枢纽记忆蒸馏＋语义相似与扩散激活双路检索|直接构造对话Agent历史记忆的组织、更新和检索机制。|Related|[论文](https://aclanthology.org/2026.acl-long.625/)|
|P037|Hierarchical Reinforcement Learning with Augmented Step-Level Transitions for LLM Agents|ACL-Q008｜如何将长交互历史压缩为可学习的局部进度状态，让层次Agent用步级转移训练并完成长程任务？|高低层策略＋局部进度摘要策略＋步级转移重构＋行为克隆与IQL|直接研究Agent层次决策状态和步级策略训练。|Related|[论文](https://aclanthology.org/2026.acl-long.318/)|
|P040|Impatient Users Confuse AI Agents: High-fidelity Simulations of Human Traits for Testing Agents|ACL-Q006｜如何可控地模拟不耐烦、困惑等用户特质，检验Agent在多轮真实行为变化下的任务鲁棒性？|对比激活差提取用户特质方向＋推理时可组合注入＋τ-trait压力测试|直接用可控用户模拟改变Agent交互条件并评估任务失效。|Related|[论文](https://aclanthology.org/2026.acl-long.1743/)|
|P046|MCP-Flow: Facilitating LLM Agents to Master Real-World, Diverse and Scaling MCP Tools|ACL-Q004｜如何从大规模真实MCP服务器与工具中自动合成并过滤多样的指令、调用和轨迹，支持Agent工具使用训练？|Web Agent发现服务器＋工具条件任务合成与进化＋多层质量过滤＋调用数据训练|直接构造Agent调用真实MCP工具所需的监督数据与轨迹。|Related|[论文](https://aclanthology.org/2026.acl-long.231/)|
|P062|SafeMCP: Proactive Power Regulation for LLM Agent Defense via Environment-Grounded Look-Ahead Reasoning|ACL-Q007｜如何在MCP服务器侧预测工具执行的环境风险，主动限制危险能力扩张而尽量保留Agent的正常任务效用？|环境动力学世界模型前瞻＋安全工具子集过滤＋危险调用即时拦截|直接约束Agent工具调用链中的危险状态转移和可用工具集合。|Related|[论文](https://aclanthology.org/2026.acl-long.522/)|
|P068|SynthAgent: Adapting Web Agents with Synthetic Supervision|ACL-Q004｜如何在新网站中自动构造环境可行的任务与低噪声轨迹，从而仅用合成监督适应Web Agent？|功能分类探索＋冲突触发任务修正＋执行后全局轨迹去噪＋SFT|直接为Web Agent跨网站适应构造可靠合成任务和行动监督。|Related|[论文](https://aclanthology.org/2026.acl-long.716/)|
|P070|Temp-R1: A Unified Autonomous Agent for Complex Temporal KGQA via Reverse Curriculum Reinforcement Learning|ACL-Q008｜如何通过反向课程强化学习，让Agent自主选择规划、时序知识检索、事实过滤和排序动作以解决复杂时序问答？|显式规划/检索/过滤/排序动作＋轨迹SFT冷启动＋GRPO与先难后易课程|直接优化Agent在时序知识图谱工具环境中的多步动作选择策略。|Related|[论文](https://aclanthology.org/2026.acl-long.1184/)|
|P077|Uncertainty Quantification in LLM Agents: Foundations, Emerging Challenges, and Opportunities|ACL-Q006｜如何形式化并量化Agent多轮交互轨迹中来自策略、工具和用户的动态不确定性，并检验现有估计器的适用边界？|动态贝叶斯轨迹分解＋既有UQ范式特例分析＋τ²-bench诊断实证|直接分析Agent交互过程的多源不确定性及其评测困难。|Related|[论文](https://aclanthology.org/2026.acl-long.738/)|
|P080|WebClipper: Efficient Evolution of Web Agents with Graph-based Trajectory Pruning|ACL-Q009｜如何识别Web Agent轨迹中对最终答案无必要贡献的工具调用，并训练出保持准确性而执行更短路径的Agent？|动作—信息依赖图＋近似最小必要DAG剪枝＋连贯性重写＋继续微调|直接针对Agent冗余搜索和工具调用的执行预算进行优化。|Related|[论文](https://aclanthology.org/2026.acl-long.988/)|
|P103|From Query to Counsel: Structured Reasoning with a Multi-Agent Framework and Dataset for Legal Consultation|ACL-Q002｜如何将复杂法律咨询组织成法律元素图，并协调草稿、法条检索与内容检查Agent生成完整的法律意见？|法律元素图＋管理Agent动态子任务路由＋格式/法条检索/内容检查迭代|直接研究围绕共同法律意见书的多Agent任务分解和动态协作。|Related|[论文](https://aclanthology.org/2026.acl-long.776/)|
|P112|ODUTQA-MDC: A Task for Open-Domain Underspecified Tabular QA with Multi-turn Dialogue-based Clarification|ACL-Q012｜在开放域表格问答中，Agent如何检测查询的意图、范围和条件缺失，并通过多轮澄清形成可执行的准确查询？|SQL子句级模糊性分类＋用户模拟澄清接口＋范围验证/表检索/SQL验证多Agent基线|直接研究Agent识别用户信息不足并主动澄清的交互能力。|Related|[论文](https://aclanthology.org/2026.acl-long.499/)|
|P121|Social Dynamics as Critical Vulnerabilities that Undermine Objective Decision-Making in LLM Collectives|ACL-Q007｜误导同伴的数量、能力、论证长度和修辞风格会怎样使多Agent系统的最终决策者偏离客观答案？|固定代表Agent与独立同伴意见，受控改变误导网络和论证特征并测量准确率变化|直接研究多Agent信息交互中错误意见对最终决策的安全与可靠性风险。|Related|[论文](https://aclanthology.org/2026.acl-long.1756/)|
|P123|Towards Robust Real-World Spreadsheet Understanding with Multi-Agent Multi-Format Reasoning|ACL-Q002｜多Agent如何在有限上下文中逐步理解大规模电子表格并减少结构提取错误传播？|局部多模态阅读构建结构草图和行列摘要，定向验证提取结构，再进行任务求解|直接研究多Agent逐区读取、结构验证和任务驱动电子表格推理。|Related|[论文](https://aclanthology.org/2026.acl-long.86/)|
|P137|Can Compact Language Models Search Like Agents? Distillation-Guided Policy Optimization for Preserving Agentic RAG Capabilities|ACL-Q008｜如何让初始能力弱的紧凑模型通过教师蒸馏与策略优化学会交替思考、搜索和回答，并避免稀疏奖励导致训练停滞？|正确教师轨迹KD冷启动＋PPO＋仅错误样本施加教师KL惩罚|直接训练紧凑模型的多轮Agentic RAG搜索决策策略。|Related|[论文](https://aclanthology.org/2026.acl-long.1751/)|
|P195|Breaking the Impasse: Dual-Scale Evolutionary Policy Training for Social Language Agents|ACL-Q008｜社会语言Agent自博弈训练中，如何识别结果分布塌缩导致的策略停滞，并恢复有用的探索与梯度信号？|比赛结果熵＋快慢EMA基线差异检测停滞＋非对称优势重塑|直接改变社会Agent自博弈的策略训练信号和探索动态。|Related|[论文](https://aclanthology.org/2026.acl-long.2096/)|
|P199|Controlling Multimodal Conversational Agents with Coverage-Enhanced Latent Actions|ACL-Q008｜如何构造覆盖充分且保留视觉信息的紧凑潜在动作空间，使多模态对话Agent能够更有效地进行强化学习探索？|跨模态投影与循环一致性＋逆动力学潜在动作码本＋码本空间RL微调|直接研究对话Agent强化学习中的动作表征和探索空间。|Related|[论文](https://aclanthology.org/2026.acl-long.191/)|
|P232|Can We Predict Before Executing Machine Learning Agents?|ACL-Q009｜在训练执行昂贵的机器学习任务中，Agent能否先预测候选方案优劣再验证少数候选，从而扩大有限预算内的有效搜索？|已验证数据分析报告＋候选成对偏好与置信度筛选＋Predict-then-Verify搜索|直接改变ML Agent昂贵代码执行与候选搜索的预算分配。|Related|[论文](https://aclanthology.org/2026.acl-long.182/)|
|P338|RISK: A Framework for GUI Agents in E-commerce Risk Management|ACL-Q008｜如何结合领域交互数据、步骤准确性及过程和难度重加权奖励，训练能完成真实电商风控任务的GUI Agent？|领域GUI轨迹精炼＋SFT冷启动＋格式/动作/过程/难度四维奖励GRPO|直接研究电商GUI Agent的领域行动训练与奖励设计。|Related|[论文](https://aclanthology.org/2026.acl-long.1720/)|
|P983|SlideAgent: Hierarchical Agentic Framework for Multi-Page Visual Document Understanding|ACL-Q002｜如何通过全局页面元素三级Agent分工提升多页视觉文档理解？|借鉴人类信息处理模型，将文档理解分解为全局（整体主题）、页面（单页特征+跨页关系）、元素（图表/文本块/图标的细粒度解析）三个层级，各级配备专用 agent，在知识构建和推理两个阶段协同工作|直接按全局、页面和元素层次分工Agent协同理解多页视觉文档。|Related|[论文](https://aclanthology.org/2026.acl-long.677/)|
|P1201|Dynamics of Cognitive Heterogeneity: Investigating Behavioral Biases in Multi-Stage Supply Chains with LLM-Based Simulation|ACL-Q002｜认知异质性与信息共享如何影响多Agent供应链模拟中的牛鞭效应？|用认知能力不同的LLM Agent模拟啤酒分销多阶段供应链，对照信息共享与集体行为|直接研究多Agent异质决策、信息共享与供应链集体行为。|Related|[论文](https://aclanthology.org/2026.acl-long.882/)|
|P1400|MemSearch-o1: Empowering Large Language Models with Reasoning-Aligned Memory Growth in Agentic Search|ACL-Q005｜搜索Agent如何在迭代检索中避免长历史造成的记忆稀释并保留细粒度证据关系？|从查询种子词生长记忆片段，按贡献函数回溯精炼，再组织全局连通记忆路径|直接研究agentic search迭代检索中的记忆稀释与证据关系保留。|Related|[论文](https://aclanthology.org/2026.acl-long.41/)|
|P1401|RAM-SD: Retrieval-Augmented Multi-agent framework for Sarcasm Detection|ACL-Q002｜多Agent如何根据讽刺类型选择推理策略并整合互补分析？|检索正反例→元规划器选预定义推理计划→专长Agent分析→整合器解释判断|直接采用元规划器、专长Agent和整合器完成类型条件的讽刺分析。|Related|[论文](https://aclanthology.org/2026.acl-long.64/)|
|P1402|A Functionality-Grounded Benchmark for Evaluating Web Agents in E-commerce Domains|ACL-Q006｜如何同时评价电商Web Agent的广泛功能覆盖、任务成功及非预期账户改动？|利用网页内容和可交互元素生成功能驱动查询，自动评价性能与安全|直接评测电商Web Agent功能覆盖、任务成功和非预期账户改动。|Related|[论文](https://aclanthology.org/2026.acl-long.68/)|
|P1403|Reinforcement Learning for Self-Improving Agent with Skill Library|ACL-Q008｜如何通过强化学习让Agent持续生成、积累并有效复用技能库？|SAGE在相似任务链上顺序rollout，累积技能并用技能整合奖励配合结果奖励|直接以顺序rollout和技能整合奖励训练Agent生成并复用技能。|Related|[论文](https://aclanthology.org/2026.acl-long.69/)|
|P1404|Grammar Search for Multi-Agent Systems|ACL-Q002｜多Agent系统能否用可组合组件的结构化搜索替代LLM自由代码生成搜索？|以固定可组合组件构成搜索空间，搜索模块化多Agent系统|直接研究通过可组合语法组件搜索多Agent系统结构。|Related|[论文](https://aclanthology.org/2026.acl-long.75/)|
|P1406|GATE: Graph-based Adaptive Tool Evolution Across Diverse Tasks|ACL-Q001｜Agent如何跨任务构建、组织和演化可靠的可复用工具？|GATE动态构建并演化分层工具图，适应不同场景|直接研究跨任务的Agent工具生成、图组织与演化复用。|Related|[论文](https://aclanthology.org/2026.acl-long.87/)|
|P1407|Mixture-of-Minds: Multi-Agent Reinforcement Learning for Table Understanding|ACL-Q002｜多Agent如何结合语义推理与精确表格操作并通过训练改进角色协作？|规划/编码/回答三角色结合代码执行，用MCTS生成伪金轨迹并RL优化|直接以规划、编码、回答三角色和MCTS-RL构成表格Agent协作工作流。|Related|[论文](https://aclanthology.org/2026.acl-long.112/)|
|P1408|COMPASS: Enhancing Agent Long-Horizon Reasoning with Evolving Context|ACL-Q005｜长程Agent如何维持相关上下文并在错误积累时进行战略干预？|执行主Agent、进度监督Meta-Thinker、维护阶段简报的Context Manager分离；附测试时扩展与小模型后训练|直接研究长程工具Agent的上下文管理、进度监督与阶段简报。|Related|[论文](https://aclanthology.org/2026.acl-long.152/)|
|P1409|Mitigating Context Interference for Reliable and Efficient Search Agents|ACL-Q005｜搜索Agent的哪些上下文引起干扰，如何通过精炼与训练减少干扰？|分析不同上下文部分，蒸馏上下文精炼器，并将精炼纳入搜索Agent的RL训练|直接诊断多轮搜索Agent上下文干扰并以蒸馏精炼器和RL训练缓解。|Related|[论文](https://aclanthology.org/2026.acl-long.160/)|
|P1411|Collaborative Chain-of-Agents for Parametric-Retrieved Knowledge Synergy|ACL-Q010｜多Agent如何协调参数知识与检索知识，减少误导证据并改善问答？|CoCoA-zero先条件知识归纳后答案推理，CoCoA合成长链多Agent轨迹微调LLM|直接以多Agent条件知识归纳和轨迹训练协调参数知识与外部证据。|Related|[论文](https://aclanthology.org/2026.acl-long.167/)|
|P1412|Retrieval as Generation: A Unified Framework with Self-Triggered Information Planning|ACL-Q001｜模型如何在生成过程中自主决定检索时机、查询改写和终止？|GRIP用控制token把检索决策并入自回归轨迹，以不同可回答程度查询的结构化数据监督|直接把检索时机、查询改写和停止作为可学习的信息获取决策。|Related|[论文](https://aclanthology.org/2026.acl-long.196/)|
|P1413|Timely Machine: Awareness of Time Makes Test-Time Scaling Agentic|ACL-Q009｜工具延迟变化时Agent如何在墙钟时间预算内安排推理和交互？|Timely-Eval改变调用频率与工具延迟，Timely-RL经SFT冷启动后训练时间预算感知规划|直接研究工具延迟下Agent的墙钟预算与时间感知规划。|Related|[论文](https://aclanthology.org/2026.acl-long.211/)|
|P1414|D2Plan: Dual-Agent Dynamic Global Planning for Complex Retrieval-Augmented Reasoning|ACL-Q001｜多跳搜索推理如何动态维护全局计划并避免被无关证据劫持？|Reasoner按反馈调整显式全局计划，Purifier筛选压缩检索内容；合成轨迹SFT加计划导向奖励RL|直接通过Reasoner全局计划与Purifier净化证据协同控制搜索推理。|Related|[论文](https://aclanthology.org/2026.acl-long.216/)|
|P1415|MedMCP-Calc: Benchmarking LLMs for Realistic Medical Calculator Scenarios via MCP Integration|ACL-Q006｜如何评价LLM在模糊医疗计算请求下的数据获取、计算器选择及多步工具工作流？|MedMCP-Calc通过MCP连接EHR与参考检索，进行过程级评测；CalcMate加入场景规划与工具增强微调|直接评测MCP医疗计算工作流的主动数据获取、工具选择与过程执行。|Related|[论文](https://aclanthology.org/2026.acl-long.221/)|
|P1416|Simple-VGC: Enhancing Visual Grounding in Multimodal Reasoning via Adaptive Tool Composition|ACL-Q001｜多模态推理如何根据视觉证据缺失类型组合补偿工具？|Simple-VGC将reuse原图、focus_area区域聚焦、zoom_in细节放大与图文token交错推理结合；构建TWI-Tools-146K|直接研究视觉推理过程中按需调用复用、区域聚焦和放大工具。|Related|[论文](https://aclanthology.org/2026.acl-long.223/)|
|P1418|AgentOCR: Reimagining Agent History via Optical Self-Compression|ACL-Q009｜Agent如何压缩不断增长的观察行动历史并兼顾任务成功与token成本？|将历史渲染为图像，分段光学缓存避免重复渲染，Agent输出压缩率并接受压缩感知奖励训练|直接压缩Agent观察行动历史，并通过奖励训练自适应压缩率。|Related|[论文](https://aclanthology.org/2026.acl-long.230/)|
|P1420|Dual-Cluster Memory Agent: Resolving Multi-Paradigm Ambiguity in Optimization Problem Solving|ACL-Q005｜Agent如何利用历史解法区分冲突建模范式并在优化求解中修错或切换路线？|历史解法分建模/编码簇，蒸馏Approach/Checklist/Pitfall，记忆增强推理中检测修复与改路|直接用历史解法双簇记忆指导Agent建模、修错和路径切换。|Related|[论文](https://aclanthology.org/2026.acl-long.266/)|
|P1421|OctoBench: Benchmarking Scaffold-Aware Instruction Following in Repository-Grounded Agentic Coding|ACL-Q006｜编码Agent完成仓库任务时是否持续遵守不同脚手架施加的指令约束？|OctoBench用完整轨迹观测和客观检查表将任务解答与规则遵循分开评分|直接评测编码Agent在多轮仓库任务中遵守脚手架指令的能力。|Related|[论文](https://aclanthology.org/2026.acl-long.269/)|
|P1422|Structured Episodic Event Memory|ACL-Q005｜Agent如何从碎片交互中恢复具有关系依赖与叙事连贯性的历史记忆？|SEEM结合事实图层与情节层，将交互转带来源指针的事件框架，以联想融合和反向来源扩展重建上下文|直接面向自主Agent长期交互组织关系事实、事件与来源回溯。|Related|[论文](https://aclanthology.org/2026.acl-long.277/)|
|P1423|MobileWorld: Benchmarking Autonomous Mobile Agents in Agent-User Interactive and MCP-Augmented Environments|ACL-Q006｜如何在可复现环境中评测移动Agent的跨应用长程任务、用户交互与MCP混合工具使用？|MobileWorld以开源应用与数据库提供可观测评估，加入用户交互/MCP任务及扩展动作空间的规划执行器|直接评测移动Agent跨应用长程任务、用户澄清和MCP混合工具交互。|Related|[论文](https://aclanthology.org/2026.acl-long.278/)|
|P1424|ACE-Router: Generalizing History-Aware Routing from MCP Tools to the Agent Web|ACL-Q001｜Agent如何利用历史依赖在大规模MCP工具和Agent网络中准确路由？|ACE-Router用依赖丰富的候选图合成多轮轨迹，训练可插拔Light Routing Agent|直接训练历史感知路由器在MCP工具和Agent网络中选择候选。|Related|[论文](https://aclanthology.org/2026.acl-long.281/)|
|P1425|TriEx: A Game-based Tri-View Framework for Explaining Internal Reasoning in Multi-Agent LLMs|ACL-Q006｜如何检查多Agent交互中自述解释、对他者信念与实际行动是否一致？|TriEx对齐第一人称行动解释、第二人称信念状态及基于环境参照的第三人称审计|直接检查多Agent解释、自身行动、他者信念与环境参照的一致性。|Related|[论文](https://aclanthology.org/2026.acl-long.292/)|
|P1426|MAS-Bench: A Unified Benchmark for Shortcut-Augmented Hybrid Mobile GUI Agents|ACL-Q006｜如何评测移动Agent组合GUI与快捷方式以及自主生成快捷方式的能力？|MAS-Bench提供API/deep-link/RPA等预定义捷径，比较预定义与生成捷径的混合执行|直接评测移动Agent组合GUI和快捷方式、生成可复用低成本工作流。|Related|[论文](https://aclanthology.org/2026.acl-long.316/)|
|P1427|Planning-Guided Tutoring with Assessment-Driven Memory for Pedagogical LLM Tutors|ACL-Q012｜多轮辅导Agent如何依据学生认知状态和学习进度自适应提供分步支架？|ScaffoldLM先从解题步骤生成教学计划，再以评估驱动记忆维护状态、步骤目标和对话并选择辅导动作|直接研究多轮辅导Agent依据教学计划、学生状态和记忆选择动作。|Related|[论文](https://aclanthology.org/2026.acl-long.325/)|
|P1428|When KV Cache Reuse Fails in Multi-Agent Systems: Cross-Candidate Interaction is Crucial for LLM Judges|ACL-Q009｜复用KV缓存时为何多Agent评价器的候选选择会偏离完整prefill决策？|定义Judge Consistency Rate，诊断跨候选注意力与位置影响，用消融检查显式跨候选交互|直接研究多Agent候选评价器复用KV缓存后选择行为失真的效率风险。|Related|[论文](https://aclanthology.org/2026.acl-long.327/)|
|P1429|ET-Agent: Incentivizing Effective Tool-Integrated Reasoning Agent via Behavior Calibration|ACL-Q008｜如何校准工具推理Agent中过多或不足调用等行为错误，而不只优化答案正确率？|ET-Agent用自演化数据飞轮提高探索能力，再以两阶段行为校准训练修正行为模式|直接训练工具推理Agent校准冗余和不足调用等行为。|Related|[论文](https://aclanthology.org/2026.acl-long.333/)|
|P1430|DeepPlanning: Benchmarking Long-Horizon Agentic Planning with Verifiable Constraints|ACL-Q006｜如何评测需要主动收集信息并满足局部及全局约束的长程Agent规划？|DeepPlanning以多日旅行和多商品购物构造可验证时间/财务等约束，并分析规划错误|直接评测Agent主动获取信息并满足局部与全局约束的长程规划。|Related|[论文](https://aclanthology.org/2026.acl-long.335/)|
|P1432|AMATA: Adaptive Multi-Agent Trajectory Alignment for Knowledge-Intensive Question Answering|ACL-Q002｜多Agent如何对齐轨迹偏好和跨Agent工具依赖以提高知识问答的事实依据？|AMATA六专长Agent协作，轨迹内偏好学习关键Agent，依赖感知DPO对齐跨Agent工具关系|直接以专长Agent和依赖感知偏好对齐协同完成知识密集问答。|Related|[论文](https://aclanthology.org/2026.acl-long.359/)|
|P1434|Mem2ActBench: A Benchmark for Evaluating Long-Term Memory Utilization in Task-Oriented Autonomous Agents|ACL-Q005｜Agent能否主动把长期记忆用于工具选择及参数填充，而非仅回答显式记忆问题？|Mem2ActBench合并异构对话工具数据并做一致性建模，从持久交互记忆链反向生成工具使用任务|直接把长期记忆是否转化为工具选择与参数填充作为Agent评测对象。|Core|[论文](https://aclanthology.org/2026.acl-long.370/)|
|P1435|Taming "Zombie" Agents: A Markov State-Aware Framework for Resilient Multi-Agent Evolution|ACL-Q002｜如何避免多Agent拓扑优化因短暂错误过早剪除仍有后续价值的Agent？|AgentRevive用Active/Standby/Terminated软状态和风险估计调度消息，再依状态剪边或终止节点|直接研究多Agent协作中暂时失效节点的软状态调度与可恢复拓扑演化。|Related|[论文](https://aclanthology.org/2026.acl-long.373/)|
|P1436|A Survey of Large Language Model-Based Search Agents|ACL-Q001｜搜索Agent的架构、优化、应用与评测路线如何组织及比较？|综述按架构、优化、应用和评价组织自主多轮搜索研究|直接梳理搜索Agent的架构、优化、应用和评测。|Related|[论文](https://aclanthology.org/2026.acl-long.374/)|
|P1437|MulVul: Retrieval-augmented Multi-Agent Code Vulnerability Detection via Cross-Model Prompt Evolution|ACL-Q002｜多Agent如何应对异质代码漏洞类型并自动优化专长检测提示？|MulVul粗粒度Router路由专长Detector并检索漏洞证据；生成器和不同执行器做跨模型提示演化|直接通过Router、专长漏洞Detector和跨模型提示演化组织多Agent任务。|Related|[论文](https://aclanthology.org/2026.acl-long.391/)|
|P1438|From Laboratory to Real-World Applications: Benchmarking Agentic Code Reasoning at the Repository Level|ACL-Q006｜如何在真实仓库中诊断编码Agent跨文件逻辑推理和证据整合的瓶颈？|RepoReason执行驱动变异重建真值，以溯因断言验证和动态程序切片分解读取/模拟/整合负担|直接以执行真值与程序切片诊断仓库级编码Agent证据整合。|Related|[论文](https://aclanthology.org/2026.acl-long.399/)|
|P1439|QBridge: Bridging Natural Language and SQL via Gold Query Rewriting with Agentic Refinement|ACL-Q003｜NL2SQL如何先修正语言到数据库语义的理解，再结合执行及语义反馈纠正SQL？|QBridge蒸馏执行验证的反向翻译为Gold Query改写器，再保守精炼中间表示并以执行有效性和语义一致性双反馈修SQL|直接以中间查询表示和执行、语义双反馈实现agentic SQL修正。|Related|[论文](https://aclanthology.org/2026.acl-long.402/)|
|P1442|Empathy in Diversity: Personalized Depression and Anxiety Therapy via Dialogue State Tracking and Patient-Aware Planning|ACL-Q012｜治疗对话Agent如何依据患者差异与对话状态制定适配的多轮策略？|MindApt整合治疗对话状态跟踪和患者感知战略规划；MindEval角色扮演评测及MindData专家标注数据配套|直接研究治疗对话Agent依据患者状态进行个性化多轮战略规划。|Related|[论文](https://aclanthology.org/2026.acl-long.424/)|
|P1443|Experience-driven Multi-turn Reinforcement Learning for GUI Agents|ACL-Q008｜GUI Agent如何以低成本专家经验进行自生成历史的多轮策略训练，减轻训练部署分布不匹配？|EMPO以专家轨迹提供匹配动作的状态转移，Patch Module补救不匹配步骤，结合未来折扣奖励和双层优势估计|直接以专家轨迹环境经验和补丁恢复训练GUI Agent自生成历史策略。|Related|[论文](https://aclanthology.org/2026.acl-long.428/)|
|P1444|OS-Sentinel: Towards Safety-Enhanced Mobile GUI Agents via Hybrid Validation in Realistic Workflows|ACL-Q007｜如何在真实移动GUI工作流中同时识别显式系统违规和依赖上下文的安全风险？|OS-Sentinel将形式验证器与VLM上下文判断器结合；MobileRisk-Live提供动态沙箱和细粒度风险轨迹标注|直接检测移动GUI Agent动作的显式系统违规和上下文风险。|Related|[论文](https://aclanthology.org/2026.acl-long.431/)|
|P1446|IEvoAgent: Evolving Conversational Agent based on User Implicit Feedback|ACL-Q012｜对话Agent如何从用户后续行为中学习隐式偏好并随反馈演化？|IEvoAgent以响应条件反馈分布矩阵估计期望奖励，结合离线KTO和动态矩阵驱动的推理时提示演化|直接从用户后续行为反馈训练和演化对话Agent。|Related|[论文](https://aclanthology.org/2026.acl-long.441/)|
|P1447|VIGIL: Defending LLM Agents Against Tool-Stream Injection via Verify-Before-Commit|ACL-Q007｜Agent如何在保留自适应工具反馈的同时防御工具流元数据和运行反馈中的注入？|VIGIL允许推测性假设生成，在提交前以意图为基准验证；SIREN提供动态依赖工具流注入案例|直接防御工具流间接提示注入，提交动作前按用户意图验证。|Related|[论文](https://aclanthology.org/2026.acl-long.443/)|
|P1448|DREAM: Deep Research Evaluation with Agentic Metrics|ACL-Q006｜没有唯一参考答案时如何评价Deep Research报告的事实、时间有效性和推理质量？|DREAM以能调用工具的评价Agent联合通用指标与自适应指标，核验覆盖、事实和推理|直接用可调用工具的评价Agent核查Deep Research报告的事实、时效与推理。|Related|[论文](https://aclanthology.org/2026.acl-long.448/)|
|P1449|Unlocking Implicit Experience: Synthesizing Tool-Use Trajectories from Text|ACL-Q004｜如何从普通文本中的隐含解题经验合成可泛化的多轮工具使用轨迹？|GEM依次做相关性过滤、工作流工具提取、轨迹grounding和复杂度精炼，再SFT专用轨迹合成器|直接从文本隐含经验构造多轮工具使用轨迹并训练专用合成器。|Related|[论文](https://aclanthology.org/2026.acl-long.452/)|
|P1450|Reinforcing Agentic Search Via Reward Density Optimization|ACL-Q008｜Agent搜索训练如何提高每单位探索成本获得的有效奖励？|InfoFlow结合子目标过程奖励、受阻路径纠正提示和双Agent精炼|直接通过子目标奖励、受阻轨迹提示和双Agent精炼提高搜索训练的奖励密度。|Related|[论文](https://aclanthology.org/2026.acl-long.467/)|
|P1451|Ready Jurist One: Benchmarking Language Agents for Legal Intelligence in Dynamic Environments|ACL-Q006｜如何评价法律Agent在动态环境中的任务执行及程序合规，而不只检查静态法律知识？|J1-ENVS提供专家指导的动态法律环境，J1-EVAL同时衡量任务表现和程序合规|直接评测动态法律环境中Agent的程序执行和任务完成。|Related|[论文](https://aclanthology.org/2026.acl-long.471/)|
|P1453|Learning from the Irrecoverable: Error-Localized Policy Optimization for Tool-Integrated LLM Reasoning|ACL-Q008｜工具推理训练如何定位第一处不可恢复错误并对关键步骤分配更有效的信用？|ELPO在固定rollout预算下二分搜索轨迹树，层次优势归因并自适应裁剪关键步及后缀|直接定位工具Agent首个不可恢复错误并进行局部信用归因与策略更新。|Related|[论文](https://aclanthology.org/2026.acl-long.504/)|
|P1454|The Confidence Dichotomy: Analyzing and Mitigating Miscalibration in Tool-Use Agents|ACL-Q008｜工具类型如何影响Agent置信度校准，如何联合优化正确率与校准？|分析证据工具与验证工具的置信度差异，RL联合优化任务准确率和校准并比较奖励设计|直接分析工具Agent置信校准并联合奖励正确率和校准。|Related|[论文](https://aclanthology.org/2026.acl-long.520/)|
|P1455|MOA: Multi-Objective Alignment for Role-Playing Agents|ACL-Q008｜角色扮演Agent如何协调指令遵循、人格一致性与表达风格等冲突目标？|MOA同时优化细粒度多维rubric，并用带思考rollout和off-policy指导提升多样性与质量|直接用多维rubric协调角色Agent指令、人格和风格目标的强化学习。|Related|[论文](https://aclanthology.org/2026.acl-long.531/)|
|P1456|Chain-of-Memory: Lightweight Memory Construction with Dynamic Evolution for LLM Agents|ACL-Q005｜Agent记忆如何以轻量构建配合更强的检索后推理，跨越召回与答题准确率间差距？|CoM将检索片段动态演化为连贯推断路径，并自适应截断无关噪声|直接研究Agent轻量记忆构建与检索后动态推断链的利用质量。|Related|[论文](https://aclanthology.org/2026.acl-long.534/)|
|P1457|MatchTIR: Fine-Grained Supervision for Tool-Integrated Reasoning via Bipartite Matching|ACL-Q008｜多轮工具RL如何区分有效、冗余和错误调用并兼顾局部步骤与全局成功？|MatchTIR将预测/真值轨迹二分匹配为轮级密集奖励，再结合轮级与轨迹级双层优势|直接通过预测与真值轨迹匹配为工具Agent提供轮级密集奖励和双层优势。|Related|[论文](https://aclanthology.org/2026.acl-long.549/)|
|P1458|RouteMoA: Dynamic Routing without Pre-Inference Boosts Efficient Mixture-of-Agents|ACL-Q002｜Mixture-of-Agents如何在不先运行全部候选模型的条件下减少协作成本和延迟？|RouteMoA用轻量预测器先筛模型，基于已有输出自评/互评校正，再按表现、成本、时延选择|直接在Mixture-of-Agents协作前预测候选价值，并以后验评价校正路由。|Related|[论文](https://aclanthology.org/2026.acl-long.558/)|
|P1459|Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards|ACL-Q004｜如何联合合成多样工具任务、稳定模拟环境和用户反馈以训练小型Agent？|SYNTHAGENT生成工具生态及欠明确指令，用户模拟器补私有信息，mock工具返回稳定结果，以子目标/交互/禁行rubric奖励训练|直接联合合成Agent工具任务、用户缺失信息交互、稳定模拟环境和rubric奖励。|Related|[论文](https://aclanthology.org/2026.acl-long.570/)|
|P1460|Generative Gamer: Learning Equilibrium Strategy by LLM-driven Dynamic Deduction|ACL-Q008｜博弈Agent如何以紧凑的动态推演轨迹学习策略而避免穷举搜索树？|GenGamer按策略置信度剪动作、价值剪状态、alpha-beta式剪分支，以Deduction Tree Reward逐步反馈训练|直接训练博弈Agent以剪枝推演和过程反馈选择策略。|Related|[论文](https://aclanthology.org/2026.acl-long.574/)|
|P1461|No More Stale Feedback: Co-Evolving Critics for Open-World Agent Learning|ACL-Q008｜开放世界Agent学习时如何使批评器跟上策略及错误分布变化，避免反馈过时？|ECHO级联rollout对初轨迹生成多诊断再修订，饱和感知增益整形并同步双轨GRPO更新策略与批评器|直接协同更新Agent策略与批评器，减轻策略分布变化导致的过时反馈。|Related|[论文](https://aclanthology.org/2026.acl-long.576/)|
|P1462|A Scalable Multi-LLM Collaboration System with Retrieval-based Selection and Exploration-Exploitation-Driven Enhancement|ACL-Q002｜多LLM协作如何扩展到新模型与任务并平衡候选探索、利用和输出质量？|SMCS以检索式先验选择模型，再由探索利用驱动的后验增强及混合评分选输出|直接用检索式先验选择和探索利用后验增强协调多LLM协作。|Related|[论文](https://aclanthology.org/2026.acl-long.578/)|
|P1463|LLM-as-Scheduler: Agentic Workflow Dynamic Scheduling|ACL-Q009｜如何按查询难度动态选择单Agent或多步骤协作工作流以减少不必要开销？|LAS用轻量gate检查Agent输出，再由LLM调度器结合查询和gate信号级联路由|直接按查询与gate信号为Agent动态选择执行工作流以控制成本。|Related|[论文](https://aclanthology.org/2026.acl-long.581/)|
|P1464|Memory-R1: Enhancing Large Language Model Agents to Manage and Utilize Memories via Reinforcement Learning|ACL-Q005｜Agent如何学习外部记忆的增删改与选择使用，而非依赖静态启发式流程？|Memory-R1分Memory Manager学习ADD/UPDATE/DELETE/NOOP和Answer Agent筛选推理，两者以结果驱动PPO/GRPO微调|直接以RL学习外部记忆增删改和回答时的选择利用。|Related|[论文](https://aclanthology.org/2026.acl-long.583/)|
|P1465|CostBench: Evaluating Multi-Turn Cost-Optimal Planning and Adaptation in Dynamic Environments for LLM Tool-Use Agents|ACL-Q006｜如何评测工具Agent在成本变化及工具故障下寻找和修订最低成本计划？|CostBench在旅行规划中提供可定制成本的原子/组合工具，以及4类动态阻断事件|直接评测工具Agent在成本变化或工具故障时规划和重规划。|Related|[论文](https://aclanthology.org/2026.acl-long.584/)|
|P1466|Interleaved Tool-Call Reasoning for Protein Function Understanding|ACL-Q001｜蛋白功能理解如何把问题分解与领域工具证据交错，替代仅依赖文本推理？|PFUA统一问题分解、领域工具调用与基于可验证中间证据的答案生成|直接将蛋白任务分解、工具调用和可验证领域证据交错。|Related|[论文](https://aclanthology.org/2026.acl-long.592/)|
|P1467|GLARE: Agentic Reasoning for Legal Judgment Prediction|ACL-Q010｜法律判断Agent如何主动比较易混淆罪名并检索排除性依据？|GLARE动态扩展混淆候选，从判例与法规中检索排除逻辑进行比较判断|直接以主动检索排除性证据支持法律Agent区分易混淆候选。|Related|[论文](https://aclanthology.org/2026.acl-long.600/)|
|P1468|DORA: A Dual-Objective Reinforcement Learning Framework for Effective and Efficient Multimodal Agentic Search|ACL-Q008｜多模态搜索Agent如何联合提高检索质量和回答正确性并减少冗余调用？|DORA以偏好少搜索的正确轨迹奖励配合搜索质量/答案正确性双优化目标|直接联合奖励搜索质量、回答正确性与较少调用以优化多模态搜索Agent。|Related|[论文](https://aclanthology.org/2026.acl-long.605/)|

**Role：**Core表示本轮代表性工作，Related表示明确相关；Edge保留于宽口径附表。

# 03｜Research Questions

## 研究问题归纳

|ID|Research Question|Papers|Sample Share|Core Papers|Main Methods|
|---|---|---|---|---|---|
|ACL-Q001|Agent如何规划并执行工具调用或信息获取步骤，以完成复杂任务？|10|10.5%|P001|工具接口与分层规划执行；动态检索与信息获取；跨任务工具复用|
|ACL-Q002|多Agent如何通过角色分工、路由与协作机制，提高共同任务完成质量？|15|15.8%|P004 / P008|角色化协作工作流；候选路由与模型选择；拓扑及状态调度|
|ACL-Q003|Agent如何把开放式答案探索与可验证的任务求解衔接起来？|2|2.1%|P003|答案探索与形式验证；执行/语义反馈修正|
|ACL-Q004|如何从带噪声的交互轨迹中构造可靠训练信号，提高Agent的行动质量？|6|6.3%|P005|任务/轨迹合成及精炼；关键步骤与偏好监督；诊断驱动定向合成|
|ACL-Q005|Agent如何组织、更新并正确利用交互记忆，支持后续决策与行动？|10|10.5%|P006 / P1434|上下文精炼与状态摘要；结构化事件及来源回溯；学习式记忆操作|
|ACL-Q006|如何可靠评测Agent的任务完成质量、交互表现及失败原因？|15|15.8%|—|功能覆盖及安全副作用；持续指令与全局约束；多工具/用户交互|
|ACL-Q007|如何识别并防御Agent交互、工具与信息链中的安全风险？|6|6.3%|—|工具流注入与提交前验证；欺骗界面行动门控；环境前瞻与工具权限|
|ACL-Q008|如何利用奖励、反馈和强化学习改善Agent的多步决策策略？|17|17.9%|—|轮级与关键动作信用分配；多目标/行为奖励校准；低成本多轮经验训练|
|ACL-Q009|如何在预算约束下提高Agent推理、上下文管理与执行效率？|6|6.3%|—|墙钟预算与工具延迟；历史压缩及缓存；执行预测及工作流调度|
|ACL-Q010|如何使Agent基于检索证据可靠判断、处理冲突并减少幻觉？|2|2.1%|—|参数/检索知识协同；候选比较与排除性证据|
|ACL-Q011|如何提高Agent在代码、GUI与具身环境中的任务执行能力？|1|1.1%|—|代码实体层的结构化动作空间|
|ACL-Q012|Agent如何通过对话、个性化与社会交互更好地理解并协助用户？|5|5.3%|—|用户状态与个性化规划；缺失信息与对话澄清；隐式行为反馈|

**Sample Share = 该问题论文数 ÷ 95。**每篇只计一个主问题。

## 问题边界

**ACL-Q004｜训练信号构造**

包含：训练任务、轨迹及监督信号的构造。

不包含：策略怎样利用这些信号学习多步决策，归入ACL-Q008。

容易混淆的相邻问题：ACL-Q008策略训练。

**ACL-Q005｜交互记忆**

包含：记忆机制及其行动应用。

不包含：通用能力及失败的可靠测量，归入ACL-Q006。

容易混淆的相邻问题：ACL-Q006 Agent评测。具体路线见[问题地图](ProblemMap.md)。

# 04｜Trend Evidence

## 趋势证据

以下区分2026样本结构、2025方法参照和跨年数量判断。现有资料支持方法对照，不支持同口径数量变化。

|ID|2026 Signal|2025 Comparable Signal|Cross-year Change|Independent Groups|Initial Reading|
|---|---|---|---|---|---|
|ACL-Q005|10篇；记忆组织、可学习操作与记忆到行动评测|[RMM](https://aclanthology.org/2025.acl-long.413/)：多粒度记忆与在线检索；[R2D2](https://aclanthology.org/2025.acl-long.1464/)：回放记忆与错误反思|—（未建立可比统计）|不作团队数量统计|当前证据不足|
|ACL-Q008|17篇；关键步信用分配、真值匹配与动态反馈|[PaSa](https://aclanthology.org/2025.acl-long.572/)：搜索Agent强化学习；[KnowSelf](https://aclanthology.org/2025.acl-long.619/)：情境标记与知识使用策略|—（未建立可比统计）|不作团队数量统计|当前证据不足|
|ACL-Q006|15篇；规则遵循、副作用与成本评价|[ToolHop](https://aclanthology.org/2025.acl-long.150/)：多跳工具使用；[MultiAgentBench](https://aclanthology.org/2025.acl-long.421/)：里程碑与协作质量评价|—（未建立可比统计）|不作团队数量统计|当前证据不足|

本次从[Paper Notes ACL2025](https://papernotes.org/ACL2025/)定向补充6篇方法参照，均核实为ACL 2025主会长文，事实依据官方元数据及摘要。这些选例不代表2025该方向总量；尚未按与2026一致的口径形成统计样本，因此不计算跨年篇数、占比变化或性能排名。

### 2025方法参照

|问题|2025工作|官方摘要支持的内容|与2026材料的对照边界|
|---|---|---|---|
|ACL-Q005|[RMM](https://aclanthology.org/2025.acl-long.413/) · [解读](https://papernotes.org/ACL2025/others/in_prospect_and_retrospect_reflective_memory_management_for_long-term_personaliz/)|多粒度交互摘要入库，依据引用证据以在线RL优化检索。|2025已研究学习式记忆检索；与Memory-R1显式增删改操作的学习目标不同。|
|ACL-Q005|[R2D2](https://aclanthology.org/2025.acl-long.1464/) · [解读](https://papernotes.org/ACL2025/llm_agent/r2d2_reflective_agentic_memory/)|回放缓冲重建已访问网页的地图，结合错误分析与策略修正。|2025已有记忆驱动行动；网页导航与跨会话记忆、Mem2ActBench不可直接横比。|
|ACL-Q008|[PaSa](https://aclanthology.org/2025.acl-long.572/) · [解读](https://papernotes.org/ACL2025/llm_agent/pasa_an_llm_agent_for_comprehensive_academic_paper_search/)|以合成学术查询训练搜索、阅读和引用选择等连续决策。|可作任务化RL训练参照；与ELPO／MatchTIR的局部信用信号需区分任务及监督条件。|
|ACL-Q008|[KnowSelf](https://aclanthology.org/2025.acl-long.619/) · [解读](https://papernotes.org/ACL2025/llm_agent/agentic_knowledgeable_self-awareness/)|为自探索轨迹加入情境标记，经两阶段训练调节外部知识使用。|关注何时使用知识；与局部信用分配、ECHO反馈时效性属于不同训练环节。|
|ACL-Q006|[ToolHop](https://aclanthology.org/2025.acl-long.150/) · [解读](https://papernotes.org/ACL2025/llm_agent/toolhop_multi_hop_tool_use/)|构造依赖明确、可本地执行的工具及可验证答案，评测多跳工具使用。|提供多步工具正确性参照，不等同于规则约束、副作用或成本最优评价。|
|ACL-Q006|[MultiAgentBench](https://aclanthology.org/2025.acl-long.421/) · [解读](https://papernotes.org/ACL2025/llm_agent/multiagentbench_evaluating_the_collaboration_and_competition_of_llm_agents/)|除任务完成外，以里程碑KPI衡量协作与竞争质量。|2025已关注过程评价；不能据2026选例认定过程指标是新出现的方向。|

**对照提示：**2025已存在学习式记忆检索、记忆驱动行动及过程评价；2026所选工作可用于比较更具体的机制和验证目标，不能据此认定这些主题首次出现或整体升温。独立团队数量不作统计，正文机制及同预算实验条件不在本轮证据范围内。

本轮研究判断见第05节；机制、反向证据与比较条件保留于[证据与研究判断](KeyFindings-Worksheet.md)。

# 05｜Key Findings

## 核心发现

本轮形成三条研究判断，事实、论文证据、推论与适用边界分列。

## F01｜记忆的价值需要沿组织、操作到行动执行分别验证

### Fact

交互记忆相关论文10篇，占95篇复核样本的10.5%。所选工作分别关注历史组织、记忆操作策略和历史信息在工具行动中的使用。

### Evidence

1. [P1422｜SEEM](https://aclanthology.org/2026.acl-long.277/)：以事实图层、情节层及来源指针组织事件，在LoCoMo、LongMemEval验证记忆组织与叙事推理。
2. [P1464｜Memory-R1](https://aclanthology.org/2026.acl-long.583/)：分别学习记忆增删改与回答时的筛选使用，以结果奖励训练管理和利用策略。
3. [P1434｜Mem2ActBench](https://aclanthology.org/2026.acl-long.370/)：通过工具任务检验历史记忆能否用于工具选择和参数落地；作者报告所测框架仍存在主动利用不足。

**2025参照：**[RMM](https://aclanthology.org/2025.acl-long.413/)：2025已研究多粒度记忆与学习式检索，说明可学习记忆管理具有既有基础；[R2D2](https://aclanthology.org/2025.acl-long.1464/)：已利用网页回放和错误反思支持后续行动，不能把记忆驱动行动视为2026新出现。

**Judgment：**记忆质量不能仅由事实回忆或问答分数代表，还需要检验历史是否在正确时机转化为正确行动。后续更值得聚焦记忆利用链中的失效位置，区分组织、检索、工具理解与参数落地错误。

**Uncertainty：**上述工作采用不同任务与验证目标；工具执行失败也可能来自推理或工具理解，现有材料不能分离各环节的因果贡献。

### Recommendation

- [x] 建议进入Stage 02
- [ ] 保持观察
- [ ] 当前不优先

进入Stage 02，优先研究历史信息到工具参数的转化与错误归因，先明确评测协议，再选择记忆机制。

**Question for Advisor：**应优先聚焦跨会话偏好到工具参数的落地，还是更一般的长期经验利用；哪一种问题边界更适合后续深入？

**Advisor Comment：**本报告无导师反馈记录。

## F02｜细粒度训练信号需要区分信用定位、监督来源与反馈时效

### Fact

策略训练相关论文17篇，占95篇复核样本的17.9%。ELPO、MatchTIR与ECHO分别从错误位置、真值轨迹和变化中的策略分布构造训练反馈。

### Evidence

1. [P1453｜ELPO](https://aclanthology.org/2026.acl-long.504/)：通过续跑搜索定位首个不可恢复错误，结合层次优势归因和局部裁剪调整策略。
2. [P1457｜MatchTIR](https://aclanthology.org/2026.acl-long.549/)：匹配预测与真值轨迹，形成轮级奖励并结合轨迹级优势，监督依赖真值轨迹。
3. [P1461｜ECHO](https://aclanthology.org/2026.acl-long.576/)：共同更新策略与批评器，使诊断反馈随Agent行为变化而调整，处理反馈过时问题。

**2025参照：**[PaSa](https://aclanthology.org/2025.acl-long.572/)：已通过强化学习训练搜索、阅读与引用选择等连续决策，但摘要未说明局部信用信号机制；[KnowSelf](https://aclanthology.org/2025.acl-long.619/)：以情境标记和两阶段训练调节外部知识使用，与错误定位和反馈时效控制不同。

**Judgment：**“奖励更细”不足以解释这些方法的差异，信号依据与更新方式决定了它们解决哪一类训练困难。比较时应同时记录真值依赖、额外续跑和反馈生成成本，再判断信用分配本身的贡献。

**Uncertainty：**任务、监督和训练预算尚未统一，改进可能部分来自额外计算或更强监督；当前不支持路线优劣排序。

### Recommendation

- [ ] 建议进入Stage 02
- [x] 保持观察
- [ ] 当前不优先

保持观察，先对照局部信用信号的可靠性和获取成本；在训练条件与预算边界明确后，再决定是否作为独立主线。

**Question for Advisor：**后续应优先研究无真值轨迹的低成本信用信号，还是先在固定任务上厘清现有监督路线的收益来源？

**Advisor Comment：**本报告无导师反馈记录。

## F03｜任务完成率之外，需要分别评价过程约束、副作用与成本

### Fact

评测相关论文15篇，占95篇复核样本的15.8%。所选基准分别检查任务结果之外的账户改动、持续规则遵循和动态成本规划。

### Evidence

1. [P1402｜Amazon-Bench](https://aclanthology.org/2026.acl-long.68/)：在电商功能任务中同时检查完成结果与非预期账户改动，评价执行的负面副作用。
2. [P1421｜OctoBench](https://aclanthology.org/2026.acl-long.269/)：记录完整轨迹，以客观检查项分开评价仓库任务解答与脚手架规则遵循。
3. [P1465｜CostBench](https://aclanthology.org/2026.acl-long.584/)：设置工具成本和动态阻断，检查Agent是否能形成成本最优计划并适应变化。

**2025参照：**[ToolHop](https://aclanthology.org/2025.acl-long.150/)：提供可验证的多跳工具使用任务，能够作为工具正确性参照，评价轴不同于副作用或成本；[MultiAgentBench](https://aclanthology.org/2025.acl-long.421/)：2025已用里程碑KPI度量过程和协作质量，因此过程评价不是2026首次出现。

**Judgment：**Agent“完成了任务”与“执行可以接受”需要分别判断。后续评测应保留成功、约束违规、副作用和成本的独立结果，并依据任务需求区分硬约束与可权衡目标，避免一个总分掩盖重要失败。

**Uncertainty：**多指标本身不保证评测可靠，检查项覆盖、成本设定和用户偏好仍会影响结论；不同环境的分数不能直接相加或排名。

### Recommendation

- [x] 建议进入Stage 02
- [ ] 保持观察
- [ ] 当前不优先

进入Stage 02作为记忆到行动研究的评测支撑，先明确错误类型与约束判据；暂不单独扩展为通用大规模基准。

**Question for Advisor：**在选定Agent任务中，哪些违规必须判为失败，哪些成本可以与成功率权衡；该协议是否足以作为独立研究贡献？

**Advisor Comment：**本报告无导师反馈记录。

# 06｜Representative Papers

## 代表论文

|Paper|Question|Why Representative|Read First|Priority|Link|
|---|---|---|---|---|---|
|P1434｜Mem2ActBench: A Benchmark for Evaluating Long-Term Memory Utilization in Task-Oriented Autonomous Agents|ACL-Q005|直接检验历史记忆向工具选择和参数的转化。|Abstract（已核对）|A|[论文](https://aclanthology.org/2026.acl-long.370/)|
|P1464｜Memory-R1: Enhancing Large Language Model Agents to Manage and Utilize Memories via Reinforcement Learning|ACL-Q005|学习外部记忆操作，适合分析管理与利用机制。|Abstract（已核对）|A|[论文](https://aclanthology.org/2026.acl-long.583/)|
|P1422｜Structured Episodic Event Memory|ACL-Q005|以结构化事件与来源组织记忆。|—|B|[论文](https://aclanthology.org/2026.acl-long.277/)|
|P1453｜Learning from the Irrecoverable: Error-Localized Policy Optimization for Tool-Integrated LLM Reasoning|ACL-Q008|通过错误定位提供局部信用信号。|—|B|[论文](https://aclanthology.org/2026.acl-long.504/)|
|P1457｜MatchTIR: Fine-Grained Supervision for Tool-Integrated Reasoning via Bipartite Matching|ACL-Q008|用真值匹配构造轮级奖励，便于比较监督依赖。|—|B|[论文](https://aclanthology.org/2026.acl-long.549/)|
|P1421｜OctoBench: Benchmarking Scaffold-Aware Instruction Following in Repository-Grounded Agentic Coding|ACL-Q006|分离任务解答与过程规则遵循。|Abstract（已核对）|A|[论文](https://aclanthology.org/2026.acl-long.269/)|
|P1465｜CostBench: Evaluating Multi-Turn Cost-Optimal Planning and Adaptation in Dynamic Environments for LLM Tool-Use Agents|ACL-Q006|评价成本最优与动态重规划。|—|B|[论文](https://aclanthology.org/2026.acl-long.584/)|

**Priority：**A为下一阶段优先阅读，B为方法对照阅读。Read First采用已核对的摘要入口，不填写没有证据位置的正文节号。

# 07｜Stage 02 Candidates

## 下一阶段候选

|Candidate|Why Continue|Current Evidence|Main Uncertainty|Owner View|
|---|---|---|---|---|
|记忆怎样转化为正确工具行动？|可对照记忆管理与行动评测。|[P1434](https://aclanthology.org/2026.acl-long.370/) / [P1464](https://aclanthology.org/2026.acl-long.583/) / [P1422](https://aclanthology.org/2026.acl-long.277/)|对话记忆收益能否迁移到工具任务？|Continue|
|怎样提供可靠且低成本的关键动作信用信号？|已有错误定位、真值匹配等路线。|[P1453](https://aclanthology.org/2026.acl-long.504/) / [P1457](https://aclanthology.org/2026.acl-long.549/) / [P1443](https://aclanthology.org/2026.acl-long.428/)|监督来源、采样及总预算是否可比？|Observe|
|怎样分开评价任务成功、过程约束与副作用？|已有规则、副作用及成本评测。|[P1402](https://aclanthology.org/2026.acl-long.68/) / [P1421](https://aclanthology.org/2026.acl-long.269/) / [P1430](https://aclanthology.org/2026.acl-long.335/)|不同环境的状态与验证协议能否对照？|Continue|

## 本阶段负责人结论

**研究安排：**以记忆到行动作为主线，以多维评测作为验证支撑；信用信号训练保留观察，不同时铺开三条独立路线。

**最值得继续深入的问题：**

1. 历史信息在记忆组织、检索、工具理解及参数落地之间怎样流动，错误主要出现在哪一环？
2. 怎样以任务成功、约束违规、副作用和成本分别测量记忆带来的真实行动收益？

|事项|本轮结论|
|---|---|
|本轮最重要的新发现|记忆机制与行为验证需要配套；信息可被回忆，不等于能被正确执行。|
|本轮最大的不确定性|不同记忆、监督和评测路线的任务、数据与预算条件不一致，因果贡献难以分离。|
|会显著改变后续结论的关键假设|所选任务必须真实依赖历史记忆；若仅凭当前输入即可完成，就无法有效判断记忆机制的贡献。|

该安排用于Stage 02问题深挖，不将研究兴趣或作者局限直接写成已证实的Open Problem。

# 08｜Revision Log

## 证据补充与判断修订

|Date|Previous View|New Evidence|Updated View|
|---|---|---|---|
|2026-11-02|前版趋势表未列2025工作，缺少问题历史位置的参照。|补充RMM、R2D2、PaSa、KnowSelf、ToolHop与MultiAgentBench六篇主会长文。|2025已有学习式记忆、记忆驱动行动和过程评价；本轮判断定位为机制与验证目标的细分，不认定首次出现或跨年升温。|

本表记录真实发生的证据补充及其对报告解释的影响，不追溯推定未记录的个人过往观点。

# 09｜Checkpoint

## 组会研究议题与当前安排

1. 记忆到行动应先选跨会话偏好、长期经验还是任务内状态作为边界？
2. 哪些指标应作为硬约束，哪些可以与成本和成功率权衡？
3. 当前路线比较还缺少哪些关键实验条件或反向证据？

|Question / Direction|本轮研究安排|主要依据|
|---|---|---|
|ACL-Q005|Continue：记忆到行动主线|F01；记忆管理方法与专门行动评测可配套分析。|
|ACL-Q008|Observe：信用信号训练|F02；监督依赖与总成本条件尚未统一。|
|ACL-Q006|Continue：验证支撑|F03；分离成功、规则、副作用与成本。|

**导师意见记录：**本报告无实际导师反馈或会议决议记录。以上是本轮研究安排，不作为导师决策。

# 10｜Deliverables

## 本阶段交付

- [x] Data Scope与统计口径
- [x] 95篇完整Paper Pool及附表入口
- [x] 12个Research Questions与样本占比
- [x] 2026证据与6篇2025方法参照
- [x] 三条Key Findings
- [x] 代表论文与阅读入口
- [x] Stage 02方向取舍及负责人结论
- [x] 证据补充与判断修订记录
- [ ] 导师Checkpoint（本报告无会议记录）

本轮报告正文与研究判断已整理完成；导师交流作为独立会议事项记录。

# 11｜Group Meeting

## 约10分钟组会汇报

|顺序|模块 / 时长|要点|
|---|---|---|
|1|Data Scope｜1 min|目录2222篇；1550篇逐项标题初筛，754篇广泛收纳；95篇样本用于问题分布。|
|2|Research Questions｜2 min|概述12个问题，区分数据构造与策略训练、记忆机制与能力评价。|
|3|Key Findings｜4 min|F01：记忆收益需行动验证；F02：训练信号需比较监督、粒度与成本；F03：成功率不足以描述执行质量。每条说明论文证据和适用边界。|
|4|Stage 02 Candidates｜2 min|记忆到行动为主线，多维评测为支撑，信用信号训练Observe。|
|5|Questions｜1 min|聚焦具体任务边界、历史依赖性、评价协议与可用训练条件。|
