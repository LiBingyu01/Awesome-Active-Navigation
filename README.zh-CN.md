# Awesome Active Navigation · 主动导航论文速览 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> 从地面机器人到无人机的主动导航精选论文：聚焦 **主动感知、语义探索、未知目标搜索、下一最佳视角、世界模型和闭环飞行**。

**语言 / Language：** 简体中文 · [English](README.md)

**75 篇论文与基准 · 6 个研究主题 · 每篇 3 点速览 · 最后更新：2026-10-21**

## 目录

- [精选必读 · Start Here](#featured)
- [范围、术语与筛选标准](#scope)
- [按研究主题浏览](#papers)
  - [地面与通用主动语义导航 (25)](#sec-a)
  - [无人机主动搜索、目标导航与主动感知 (9)](#sec-b)
  - [无人机 VLN / VLA 与迁移基线 (17)](#sec-c)
  - [经典边界探索、下一最佳视角与三维建图 (6)](#sec-d)
  - [普通导航、VLN 与 VLA 基线 (13)](#sec-e)
  - [数据集、仿真器与评测基础设施 (5)](#sec-f)
- [研究路线与实验建议](#roadmap)
- [贡献和维护](#contributing)

<a id="featured"></a>

## 精选必读 · Start Here

此处按照研究价值与任务契合度推荐，并不代表客观排名。

| 论文 | 推荐理由 |
| :--- | :--- |
| [**UAST**](https://openaccess.thecvf.com/content/CVPR2026/html/Qin_UAST_Unified_Active_Search_and_Tracking_for_Arbitrary_Targets_with_CVPR_2026_paper.html) · CVPR 2026 | 主动搜索与长期无人机目标追踪的直接连接点。 |
| [**APEX**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_APEX_A_Decoupled_Memory-based_Explorer_for_Asynchronous_Aerial_Object_Goal_CVPR_2026_paper.html) · CVPR 2026 | 具有异步记忆、决策与搜索模块的空中目标搜索基线。 |
| [**OctoMem-Agent**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhou_Memory-Augmented_Scene_Understanding_and_Exploration_for_Open-World_Aerial_Object-Goal_Navigation_CVPR_2026_paper.html) · CVPR 2026 | 未知三维前沿 + 指令条件化八叉树记忆。 |
| [**STEM**](https://link.springer.com/article/10.1007/s10514-026-10247-6) · Autonomous Robots 2026 | 语义信息增益与空中三维观察位姿选择。 |
| [**WoMAP**](https://proceedings.mlr.press/v305/yin25b.html) · CoRL 2025 | 利用世界模型开展主动目标定位与信息获取。 |
| [**VLFM**](https://doi.org/10.1109/ICRA57147.2024.10610712) · ICRA 2024 | 训练自由的 VLM 前沿导航与真实地面平台部署。 |
| [**PONI**](https://openaccess.thecvf.com/content/CVPR2022/html/Ramakrishnan_PONI_Potential_Functions_for_ObjectGoal_Navigation_With_Interaction-Free_Learning_CVPR_2022_paper.html) · CVPR 2022 | “去哪找”与“如何走”解耦的基础工作。 |
| [**UAV-ON**](https://arxiv.org/abs/2508.00288) · arXiv 2025 | 没有路线提示的空中 ObjectNav 数据和任务入口。 |
| [**AerialVLN**](https://openaccess.thecvf.com/content/ICCV2023/html/Liu_AerialVLN_Vision-and-Language_Navigation_for_UAVs_ICCV_2023_paper.html) · ICCV 2023 | 经典空中指令跟随基准，可作为非主动导航对照。 |
| [**OpenFly**](https://arxiv.org/abs/2502.18041) · arXiv 2025 | 可扩展的空中 VLN 数据生成与连续控制基线。 |

<a id="scope"></a>

## 范围、术语与筛选标准

**严格的 Active Navigation**：策略应明确把移动或传感器视角选择用于**主动获取信息、减少不确定性、扩大探索覆盖、验证候选目标**，而非仅依据目标指令做路径跟随。

**相关任务**：ObjectNav、InstanceNav、Active Target Search、Active SLAM、Frontier Exploration、NBV、Information-Gain Planning、Active Tracking。**对照任务**：PointNav、ImageNav、VLN、VLA、普通路径规划。

**标签说明：** `Core` = 直接属于主动搜索/探索/视点选择；`Adjacent` = 对研究很重要，但主动信息获取非核心贡献；`Baseline` = 普通导航/VLN/VLA 方法；`Benchmark` = 数据、评测或仿真平台。

无人机文献区分 **空中 ObjectNav（无详细路径指令的未知目标搜索）** 与 **空中 VLN（根据语言指令跟随导航）**，以免任务定义混淆。

<a id="papers"></a>

## 按研究主题浏览 · Papers

<a id="sec-a"></a>

### 地面与通用主动语义导航 (25)

| 论文标题 | 发表位置 / 状态 | 研究关联 | 核心创新 · 3 点 |
| :--- | :--- | :--- | :--- |
| [**Object Goal Navigation using Goal-Oriented Semantic Exploration**](https://proceedings.neurips.cc/paper/2020/hash/2c75cf2681788adaca63aa95ae028b22-Abstract.html) | NeurIPS 2020 | `Core` | **1 · 任务** — 在陌生室内环境搜索指定类别目标<br>**2 · 方法** — 构建在线语义地图并进行目标导向探索<br>**3 · 亮点** — 模块化语义 ObjectNav 的基础工作 |
| [**PONI: Potential Functions for ObjectGoal Navigation With Interaction-Free Learning**](https://openaccess.thecvf.com/content/CVPR2022/html/Ramakrishnan_PONI_Potential_Functions_for_ObjectGoal_Navigation_With_Interaction-Free_Learning_CVPR_2022_paper.html) | CVPR 2022 | `Core` | **1 · 任务** — 将“去哪里找”与“如何到达”解耦<br>**2 · 方法** — 根据不完整地图预测目标与区域势函数<br>**3 · 亮点** — 无交互训练搜索策略，适合迁移至 UAV |
| [**L3MVN: Leveraging Large Language Models for Visual Target Navigation**](https://arxiv.org/abs/2304.05501) | IROS 2023 | `Core` | **1 · 任务** — 用语言常识辅助视觉目标搜索<br>**2 · 方法** — 利用 LLM 语义信息筛选探索边界<br>**3 · 亮点** — 探索零样本迁移并验证实机可行性 |
| [**ESC: Exploration with Soft Commonsense Constraints for Zero-shot Object Navigation**](https://proceedings.mlr.press/v202/zhou23r.html) | ICML 2023 | `Core` | **1 · 任务** — 对未见类别执行目标搜索<br>**2 · 方法** — 结合开放词汇定位与软常识约束<br>**3 · 亮点** — 以零样本探索替代任务专用策略训练 |
| [**VLFM: Vision-Language Frontier Maps for Zero-Shot Semantic Navigation**](https://doi.org/10.1109/ICRA57147.2024.10610712) | ICRA 2024 | `Core` | **1 · 任务** — 为语义目标主动选择高价值探索边界<br>**2 · 方法** — 构建 VLM 条件化空间价值图<br>**3 · 亮点** — 可直接参考其零训练与实体机器人部署 |
| [**VoroNav: Voronoi-based Zero-shot Object Navigation with Large Language Model**](https://proceedings.mlr.press/v235/wu24u.html) | ICML 2024 | `Core` | **1 · 任务** — 面向零样本目标搜索的高效探索<br>**2 · 方法** — 使用约化 Voronoi 图描述可选路径<br>**3 · 亮点** — 让 LLM 决策探索航点 |
| [**OpenFMNav: Towards Open-Set Zero-Shot Object Navigation via Vision-Language Foundation Models**](https://aclanthology.org/2024.findings-naacl.24/) | Findings of NAACL 2024 | `Core` | **1 · 任务** — 理解开放类别自然语言导航目标<br>**2 · 方法** — 利用基础模型构建语义评分地图<br>**3 · 亮点** — 结合语言推理执行探索与目标逼近 |
| [**SG-Nav: Online 3D Scene Graph Prompting for LLM-based Zero-shot Object Navigation**](https://arxiv.org/abs/2410.08189) | NeurIPS 2024 | `Core` | **1 · 任务** — 搜索中在线维护结构化场景表征<br>**2 · 方法** — 以三维场景图驱动 LLM 推理<br>**3 · 亮点** — 利用语义关系与重新感知寻找目标 |
| [**Instance-aware Exploration-Verification-Exploitation for Instance ImageGoal Navigation**](https://openaccess.thecvf.com/content/CVPR2024/html/Lei_Instance-aware_Exploration-Verification-Exploitation_for_Instance_ImageGoal_Navigation_CVPR_2024_paper.html) | CVPR 2024 | `Core` | **1 · 任务** — 搜索特定实例而非仅定位类别<br>**2 · 方法** — 主动切换探索、验证与利用动作<br>**3 · 亮点** — 通过接近验证区分外观相近的干扰目标 |
| [**MOPA: Modular Object Navigation With PointGoal Agents**](https://openaccess.thecvf.com/content/WACV2024/html/Raychaudhuri_MOPA_Modular_Object_Navigation_With_PointGoal_Agents_WACV_2024_paper.html) | WACV 2024 | `Adjacent` | **1 · 任务** — 将 ObjectNav 划分为检测、建图、探索与运动<br>**2 · 方法** — 复用 PointNav 控制器而非重训全部模块<br>**3 · 亮点** — 统一比较不同探索策略，适合作为消融平台 |
| [**Imagine Before Go: Self-Supervised Generative Map for Object Goal Navigation**](https://openaccess.thecvf.com/content/CVPR2024/html/Zhang_Imagine_Before_Go_Self-Supervised_Generative_Map_for_Object_Goal_Navigation_CVPR_2024_paper.html) | CVPR 2024 | `Core` | **1 · 任务** — 在 ObjectNav 中推断未观测环境<br>**2 · 方法** — 构建自监督生成式地图先验<br>**3 · 亮点** — 利用预测地图提前确定搜索方向 |
| [**ForesightNav: Learning Scene Imagination for Efficient Exploration**](https://openaccess.thecvf.com/content/CVPR2025W/OpenSUN3D/html/Shah_ForesightNav_Learning_Scene_Imagination_for_Efficient_Exploration_CVPRW_2025_paper.html) | CVPR Workshops 2025 | `Core` | **1 · 任务** — 预测可见区域背后的占据与语义布局<br>**2 · 方法** — 基于想象场景挑选长期探索目标<br>**3 · 亮点** — 评估对 PointNav 与 ObjectNav 的帮助 |
| [**Active Perception Meets Rule-Guided RL: A Two-Phase Approach for Precise Object Navigation in Complex Environments**](https://openaccess.thecvf.com/content/ICCV2025/html/Qin_Active_Perception_Meets_Rule-Guided_RL_A_Two-Phase_Approach_for_Precise_ICCV_2025_paper.html) | ICCV 2025 | `Core` | **1 · 任务** — 兼顾长程目标搜索与末端精确定位<br>**2 · 方法** — 规则引导强化学习探索和主动末端感知<br>**3 · 亮点** — 适合研究从发现目标到可交互位姿的切换 |
| [**CogNav: Cognitive Process Modeling for Object Goal Navigation with LLMs**](https://openaccess.thecvf.com/content/ICCV2025/html/Cao_CogNav_Cognitive_Process_Modeling_for_Object_Goal_Navigation_with_LLMs_ICCV_2025_paper.html) | ICCV 2025 | `Core` | **1 · 任务** — 把目标搜索划分为可解释认知状态<br>**2 · 方法** — 构建异构认知地图并用 LLM 管理状态切换<br>**3 · 亮点** — 从探索逐步过渡到目标识别与确认 |
| [**Function-centric Bayesian Network for Zero-Shot Object Goal Navigation**](https://openaccess.thecvf.com/content/ICCV2025/html/Zhang_Function-centric_Bayesian_Network_for_Zero-Shot_Object_Goal_Navigation_ICCV_2025_paper.html) | ICCV 2025 | `Core` | **1 · 任务** — 通过物体用途与场景关系推断隐藏目标<br>**2 · 方法** — 建立物体、场景、功能之间的贝叶斯网络<br>**3 · 亮点** — 按照目标位置后验概率挑选航点 |
| [**Context-Nav: Context-Driven Exploration and Viewpoint-Aware 3D Spatial Reasoning for Instance Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Jang_Context-Nav_Context-Driven_Exploration_and_Viewpoint-Aware_3D_Spatial_Reasoning_for_Instance_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · 任务** — 在同类实例干扰下寻找文本指定目标<br>**2 · 方法** — 利用完整上下文描述对前沿区域排序<br>**3 · 亮点** — 从候选观察视角校验三维空间关系 |
| [**TrajRAG: Retrieving Geometric-Semantic Experience for Zero-Shot Object Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_TrajRAG_Retrieving_Geometric-Semantic_Experience_for_Zero-Shot_Object_Navigation_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · 任务** — 复用历史探索轨迹经验<br>**2 · 方法** — 将轨迹编码为紧凑拓扑-极坐标记忆<br>**3 · 亮点** — 检索相关轨迹以辅助选择探索边界 |
| [**UniGoal: Towards Universal Zero-shot Goal-oriented Navigation**](https://openaccess.thecvf.com/content/CVPR2025/papers/Yin_UniGoal_Towards_Universal_Zero-shot_Goal-oriented_Navigation_CVPR_2025_paper.pdf) | CVPR 2025 | `Core` | **1 · 任务** — 统一类别、图像与语言导航目标<br>**2 · 方法** — 在线构建场景图并执行目标图匹配<br>**3 · 亮点** — 根据匹配完整度切换搜索策略 |
| [**Multi-Scale Gaussian-Language Map for Zero-shot Embodied Navigation and Reasoning**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_Multi-Scale_Gaussian-Language_Map_for_Zero-shot_Embodied_Navigation_and_Reasoning_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · 任务** — 融合三维几何与自然语言的可查询记忆<br>**2 · 方法** — 在高斯表示中存储实例及区域语义<br>**3 · 亮点** — 支撑零样本目标定位和空间推理 |
| [**WoMAP: World Models For Embodied Open-Vocabulary Object Localization**](https://proceedings.mlr.press/v305/yin25b.html) | CoRL 2025 | `Core` | **1 · 任务** — 在部分可观测环境中执行主动物体定位<br>**2 · 方法** — 结合 3DGS 生成数据与开放词汇检测奖励<br>**3 · 亮点** — 以潜在世界模型约束动作选择 |
| [**InstructNav: Zero-shot System for Generic Instruction Navigation in Unexplored Environment**](https://arxiv.org/abs/2406.04882) | CoRL 2024 | `Adjacent` | **1 · 任务** — 支持多种自然语言导航任务<br>**2 · 方法** — 以动态导航推理和多源价值图规划<br>**3 · 亮点** — 零样本迁移至 ObjectNav 及连续 VLN |
| [**GOAT-Bench: A Benchmark for Multi-Modal Lifelong Navigation**](https://openaccess.thecvf.com/content/CVPR2024/html/Khanna_GOAT-Bench_A_Benchmark_for_Multi-Modal_Lifelong_Navigation_CVPR_2024_paper.html) | CVPR 2024 | `Benchmark` | **1 · 任务** — 定义连续多目标类别、图像及文本导航<br>**2 · 方法** — 评测持续任务中的场景记忆复用<br>**3 · 亮点** — 连接主动探索与终身语义导航 |
| [**DARE: Diffusion Policy for Autonomous Robot Exploration**](https://doi.org/10.1109/ICRA55743.2025.11128196) | ICRA 2025 | `Core` | **1 · 任务** — 在未知环境生成长时探索轨迹<br>**2 · 方法** — 从专家示范训练扩散路径策略<br>**3 · 亮点** — 由局部地图推断未观察区域布局 |
| [**CogniPlan: Uncertainty-Guided Path Planning with Conditional Generative Layout Prediction**](https://proceedings.mlr.press/v305/wang25d.html) | CoRL 2025 | `Core` | **1 · 任务** — 未知环境结构下制定探索路径<br>**2 · 方法** — 通过生成式布局补全估计不确定区域<br>**3 · 亮点** — 将场景预测的不确定性用于规划 |
| [**SOON: Scenario Oriented Object Navigation With Graph-Based Exploration**](https://openaccess.thecvf.com/content/CVPR2021/html/Zhu_SOON_Scenario_Oriented_Object_Navigation_With_Graph-Based_Exploration_CVPR_2021_paper.html) | CVPR 2021 | `Core` | **1 · 任务** — 提出任意起点、根据场景描述找目标的任务<br>**2 · 方法** — 使用图结构进行长程目标探索<br>**3 · 亮点** — 同时要求导航到附近并确认目标位置 |

<a id="sec-b"></a>

### 无人机主动搜索、目标导航与主动感知 (9)

| 论文标题 | 发表位置 / 状态 | 研究关联 | 核心创新 · 3 点 |
| :--- | :--- | :--- | :--- |
| [**UAV-ON: A Benchmark for Open-World Object Goal Navigation with Aerial Agents**](https://arxiv.org/abs/2508.00288) | arXiv 2025 | `Benchmark` | **1 · 任务** — 定义无需详细路线指令的空中 ObjectNav<br>**2 · 方法** — 提供开放环境与实例级搜索目标<br>**3 · 亮点** — 揭示空中三维探索与语义定位难题 |
| [**APEX: A Decoupled Memory-based Explorer for Asynchronous Aerial Object Goal Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_APEX_A_Decoupled_Memory-based_Explorer_for_Asynchronous_Aerial_Object_Goal_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · 任务** — 复杂空中场景下自主探索并搜索目标<br>**2 · 方法** — 三维语义地图与强化学习动作决策协同<br>**3 · 亮点** — 异步目标确认以缓解 VLM 推理延迟 |
| [**Memory-Augmented Scene Understanding and Exploration for Open-World Aerial Object-Goal Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhou_Memory-Augmented_Scene_Understanding_and_Exploration_for_Open-World_Aerial_Object-Goal_Navigation_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · 任务** — 面向空中 ObjectNav 的指令驱动探索<br>**2 · 方法** — 以自适应八叉树记录已见空间与未知前沿<br>**3 · 亮点** — 查询目标相关记忆以指导三维搜索 |
| [**STEM: Semantic target search and exploration using MAVs in cluttered environments**](https://link.springer.com/article/10.1007/s10514-026-10247-6) | Autonomous Robots 2026 | `Core` | **1 · 任务** — 微型无人机在拥挤三维环境搜索目标<br>**2 · 方法** — 联合语义相关性与空间覆盖目标<br>**3 · 亮点** — 对更可能发现目标的三维观察位姿排序 |
| [**UAST: Unified Active Search and Tracking for Arbitrary Targets with UAVs**](https://openaccess.thecvf.com/content/CVPR2026/html/Qin_UAST_Unified_Active_Search_and_Tracking_for_Arbitrary_Targets_with_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · 任务** — 统一任意目标的主动搜索与持续追踪<br>**2 · 方法** — 用 RGB-D 感知和搜索恢复机制处理丢失<br>**3 · 亮点** — 将目标可见性与飞行轨迹控制耦合 |
| [**Dual-Layer Semantic-Spatial Belief Mapping for Aerial Object Goal Navigation**](https://arxiv.org/abs/2609.08164) | arXiv 2026 | `Core` | **1 · 任务** — 维护随观察更新的目标位置置信图<br>**2 · 方法** — 区分场景直觉和明确目标证据<br>**3 · 亮点** — 协调区域探索、重复访问与目标确认 |
| [**Reinforcement Learning for Active Perception in Autonomous Navigation**](https://arxiv.org/abs/2602.01266) | arXiv 2026 | `Core` | **1 · 任务** — 联合控制飞行运动与主动相机视角<br>**2 · 方法** — 将体素信息增益加入导航奖励<br>**3 · 亮点** — 以主动观察提高避障安全性 |
| [**Parse, Search, and Confirmation: Training-Free Aerial Vision-and-Dialog Navigation with Chain-of-Thought Reasoning and Structured Spatial Memory**](https://openaccess.thecvf.com/content/CVPR2026/html/Qi_Parse_Search_and_Confirmation_Training-Free_Aerial_Vision-and-Dialog_Navigation_with_Chain-of-Thought_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · 任务** — 从空中对话指令搜索并确认地标<br>**2 · 方法** — 采用解析、搜索、确认的分阶段推理<br>**3 · 亮点** — 无需特定任务训练，维护结构化空间记忆 |
| [**Maximizing aerial detection of organic objects in non-exhaustively searchable survey area**](https://openaccess.thecvf.com/content/CVPR2025W/V4A/html/Niaraki_Maximizing_aerial_detection_of_organic_objects_in_non-exhaustively_searchable_survey_CVPRW_2025_paper.html) | CVPR Workshops 2025 | `Core` | **1 · 任务** — 覆盖不完区域中最大化空中目标发现<br>**2 · 方法** — 根据已发现目标与风场规划三维航迹<br>**3 · 亮点** — 考虑有限飞行预算与搜索效率 |

<a id="sec-c"></a>

### 无人机 VLN / VLA 与迁移基线 (17)

| 论文标题 | 发表位置 / 状态 | 研究关联 | 核心创新 · 3 点 |
| :--- | :--- | :--- | :--- |
| [**AerialVLN: Vision-and-Language Navigation for UAVs**](https://openaccess.thecvf.com/content/ICCV2023/html/Liu_AerialVLN_Vision-and-Language_Navigation_for_UAVs_ICCV_2023_paper.html) | ICCV 2023 | `Baseline` | **1 · 任务** — 建立连续三维无人机视觉语言导航任务<br>**2 · 方法** — 模拟城市环境与语言航路描述<br>**3 · 亮点** — 揭示高度控制和三维动作空间困难 |
| [**Aerial Vision-and-Dialog Navigation**](https://arxiv.org/abs/2205.12219) | arXiv 2022 | `Baseline` | **1 · 任务** — 研究人机对话辅助的空中导航<br>**2 · 方法** — 收集对话轨迹与人类注意数据<br>**3 · 亮点** — 根据对话历史预测后续航点 |
| [**Towards Realistic UAV Vision-Language Navigation: Platform, Benchmark, and Methodology**](https://arxiv.org/abs/2410.07087) | arXiv 2024 | `Baseline` | **1 · 任务** — 建立真实运动约束的 OpenUAV/TravelUAV 平台<br>**2 · 方法** — 提出带辅助指令的无人机目标搜索设定<br>**3 · 亮点** — 结合 MLLM 推理与分层轨迹控制 |
| [**OpenFly: A Versatile Toolchain and Large-scale Benchmark for Aerial Vision-Language Navigation**](https://arxiv.org/abs/2502.18041) | arXiv 2025 | `Benchmark` | **1 · 任务** — 构建可扩展的无人机 VLN 数据引擎<br>**2 · 方法** — 融合多种室外渲染器生成飞行轨迹<br>**3 · 亮点** — 提供基于历史关键帧的导航基线 |
| [**CityNav: A Large-Scale Dataset for Real-World Aerial Navigation**](https://openaccess.thecvf.com/content/ICCV2025/html/Lee_CityNav_A_Large-Scale_Dataset_for_Real-World_Aerial_Navigation_ICCV_2025_paper.html) | ICCV 2025 | `Benchmark` | **1 · 任务** — 在真实城市地理环境评测空中 VLN<br>**2 · 方法** — 配对飞行路线与自然语言目的地描述<br>**3 · 亮点** — 验证地理语义地图对导航的帮助 |
| [**CityNavAgent: Aerial Vision-and-Language Navigation with Hierarchical Semantic Planning and Global Memory**](https://aclanthology.org/2025.acl-long.1511/) | ACL 2025 | `Adjacent` | **1 · 任务** — 将长程无人机指令分解为语义子目标<br>**2 · 方法** — 建立历史轨迹的全局拓扑记忆<br>**3 · 亮点** — 以 LLM 推理逐级完成导航 |
| [**UAV-Flow Colosseo: A Real-World Benchmark for Flying-on-a-Word UAV Imitation Learning**](https://arxiv.org/abs/2505.15725) | arXiv 2025 | `Benchmark` | **1 · 任务** — 面向细粒度语言条件无人机运动<br>**2 · 方法** — 记录真实飞手轨迹与原子动作指令<br>**3 · 亮点** — 补充普通高层 VLN 缺乏的底层动作评测 |
| [**HTNav: A Hybrid Navigation Framework with Tiered Structure for Urban Aerial Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Fan_HTNav_A_Hybrid_Navigation_Framework_with_Tiered_Structure_for_Urban_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · 任务** — 面向具有泛化需求的长程空中 VLN<br>**2 · 方法** — 结合分阶段模仿学习与强化学习<br>**3 · 亮点** — 改善城市空间布局下的探索表现 |
| [**LookasideVLN: Direction-Aware Aerial Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Ning_LookasideVLN_Direction-Aware_Aerial_Vision-and-Language_Navigation_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · 任务** — 将方向词与无人机自身视角对齐<br>**2 · 方法** — 构建自我中心的方向地标关系图<br>**3 · 亮点** — 利用历史地标知识优化路线规划 |
| [**AerialVLA: A Vision-Language-Action Model for UAV Navigation via Minimalist End-to-End Control**](https://arxiv.org/abs/2603.14363) | arXiv 2026 | `Baseline` | **1 · 任务** — 将语言与机载视觉映射为连续动作<br>**2 · 方法** — 用双视图感知与机载方向线索决策<br>**3 · 亮点** — 评测连续飞行控制与落点操作 |
| [**LongFly: Long-Horizon UAV Vision-and-Language Navigation with Spatiotemporal Context Integration**](https://arxiv.org/abs/2512.22010) | arXiv 2025 | `Adjacent` | **1 · 任务** — 研究长程无人机语言导航的时间依赖<br>**2 · 方法** — 压缩历史图像为时空上下文<br>**3 · 亮点** — 融合轨迹历史与当前观察作航点预测 |
| [**Fly0: Decoupling Semantic Grounding from Geometric Planning for Zero-Shot Aerial Navigation**](https://arxiv.org/abs/2602.15875) | arXiv 2026 | `Adjacent` | **1 · 任务** — 将 VLM 语义定位与安全运动规划解耦<br>**2 · 方法** — 通过深度把像素目标投影至三维坐标<br>**3 · 亮点** — 降低连续 VLM 调用带来的控制不稳定 |
| [**OnFly: Onboard Zero-Shot Aerial Vision-Language Navigation toward Safety and Efficiency**](https://arxiv.org/abs/2603.10682) | arXiv 2026 | `Adjacent` | **1 · 任务** — 实现全机载零样本语言导航<br>**2 · 方法** — 将目标提议与任务进度监控分离<br>**3 · 亮点** — 联合语义几何校验与安全航迹规划 |
| [**RecoverFly: A Failure-Aware Reinforcement Learning Post-Training Framework for Aerial Vision-Language Navigation**](https://arxiv.org/abs/2608.09467) | arXiv 2026 | `Adjacent` | **1 · 任务** — 研究无人机 VLN 失败后的恢复能力<br>**2 · 方法** — 强化学习后训练中重放困难失败轨迹<br>**3 · 亮点** — 提升端到端 UAV-VLA 闭环鲁棒性 |
| [**Beyond Matching to Tiles: Bridging Unaligned Aerial and Satellite Views for Vision-Only UAV Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Liu_Beyond_Matching_to_Tiles_Bridging_Unaligned_Aerial_and_Satellite_Views_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · 任务** — 利用机载图像与卫星视图对应实现导航<br>**2 · 方法** — 处理空中与俯视图几何不匹配<br>**3 · 亮点** — 为 GNSS 不可靠环境提供视觉定位线索 |
| [**Is your VLM Sky-Ready? A Comprehensive Spatial Intelligence Benchmark for UAV Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_Is_your_VLM_Sky-Ready_A_Comprehensive_Spatial_Intelligence_Benchmark_for_CVPR_2026_paper.html) | CVPR 2026 | `Benchmark` | **1 · 任务** — 检验 VLM 在无人机空间智能中的能力<br>**2 · 方法** — 覆盖方向、距离、高度与降落安全等任务<br>**3 · 亮点** — 揭示通用 VLM 作为机载感知器的局限 |
| [**AirSim360: A Panoramic Simulation Platform within Drone View**](https://openaccess.thecvf.com/content/CVPR2026/html/Ge_AirSim360_A_Panoramic_Simulation_Platform_within_Drone_View_CVPR_2026_paper.html) | CVPR 2026 | `Benchmark` | **1 · 任务** — 模拟移动无人机的全向视觉观察<br>**2 · 方法** — 提供全景几何、语义与实例标注<br>**3 · 亮点** — 支持自动飞行轨迹与导航数据生成 |

<a id="sec-d"></a>

### 经典边界探索、下一最佳视角与三维建图 (6)

| 论文标题 | 发表位置 / 状态 | 研究关联 | 核心创新 · 3 点 |
| :--- | :--- | :--- | :--- |
| [**A Frontier-Based Approach for Autonomous Exploration**](https://doi.org/10.1109/CIRA.1997.613851) | CIRA 1997 | `Core` | **1 · 任务** — 提出将已知未知边界作为探索目标<br>**2 · 方法** — 朝可到达的前沿区域移动<br>**3 · 亮点** — 构成现代主动探索的经典基线 |
| [**Receding Horizon Next-Best-View Planner for 3D Exploration**](https://doi.org/10.1109/ICRA.2016.7487281) | ICRA 2016 | `Core` | **1 · 任务** — 选择能观察最多未知三维空间的视点<br>**2 · 方法** — 在采样搜索树上评估信息增益<br>**3 · 亮点** — 仅执行首段航迹并在线滚动重规划 |
| [**FUEL: Fast UAV Exploration using Incremental Frontier Structure and Hierarchical Planning**](https://arxiv.org/abs/2010.11561) | IEEE RA-L 2021 | `Core` | **1 · 任务** — 面向无人机未知区域的高效覆盖探索<br>**2 · 方法** — 增量更新 frontier 并执行分层规划<br>**3 · 亮点** — 输出高效近最短时间探索轨迹 |
| [**TARE: A Hierarchical Framework for Efficiently Exploring Complex 3D Environments**](https://www.roboticsproceedings.org/rss17/p018.html) | RSS 2021 | `Core` | **1 · 任务** — 探索复杂未知三维环境<br>**2 · 方法** — 局部密集规划与全局稀疏覆盖协同<br>**3 · 亮点** — 同时验证地面机器人与空中平台 |
| [**FAEL: Fast Autonomous Exploration for Large-scale Environments With a Mobile Robot**](https://doi.org/10.1109/LRA.2023.3236573) | IEEE RA-L 2023 | `Core` | **1 · 任务** — 面向大规模环境提升自主探索效率<br>**2 · 方法** — 优化候选探索点筛选与路径规划<br>**3 · 亮点** — 可作为地面机器人与无人机算法对照 |
| [**ARiADNE: A Reinforcement Learning Approach Using Attention-Based Deep Networks for Exploration**](https://doi.org/10.1109/ICRA48891.2023.10160565) | ICRA 2023 | `Core` | **1 · 任务** — 将未知空间探索转化为学习型决策<br>**2 · 方法** — 使用注意力网络选择下一探索目标<br>**3 · 亮点** — 为后续扩散探索策略提供对照 |

<a id="sec-e"></a>

### 普通导航、VLN 与 VLA 基线 (13)

| 论文标题 | 发表位置 / 状态 | 研究关联 | 核心创新 · 3 点 |
| :--- | :--- | :--- | :--- |
| [**Vision-and-Language Navigation: Interpreting Visually-Grounded Navigation Instructions in Real Environments**](https://openaccess.thecvf.com/content_cvpr_2018/html/Anderson_Vision-and-Language_Navigation_Interpreting_CVPR_2018_paper.html) | CVPR 2018 | `Baseline` | **1 · 任务** — 提出 Room-to-Room 室内语言导航任务<br>**2 · 方法** — 将人类指令与真实室内全景视图关联<br>**3 · 亮点** — 建立指令跟随的基础评测方式 |
| [**Reinforced Cross-Modal Matching and Self-Supervised Imitation Learning for Vision-Language Navigation**](https://openaccess.thecvf.com/content_CVPR_2019/html/Wang_Reinforced_Cross-Modal_Matching_and_Self-Supervised_Imitation_Learning_for_Vision-Language_Navigation_CVPR_2019_paper.html) | CVPR 2019 | `Baseline` | **1 · 任务** — 对齐自然语言指令、轨迹与视觉观察<br>**2 · 方法** — 结合跨模态奖励与自我模仿学习<br>**3 · 亮点** — 改善未见场景指令导航泛化 |
| [**Think Global, Act Local: Dual-Scale Graph Transformer for Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2022/html/Chen_Think_Global_Act_Local_Dual-Scale_Graph_Transformer_for_Vision-and-Language_Navigation_CVPR_2022_paper.html) | CVPR 2022 | `Baseline` | **1 · 任务** — 联合局部语言对齐与全局动作规划<br>**2 · 方法** — 在线生成拓扑导航图<br>**3 · 亮点** — 适合对比地图驱动的 VLN 策略 |
| [**ETPNav: Evolving Topological Planning for Vision-Language Navigation in Continuous Environments**](https://github.com/ifundo/ETPNav) | IEEE TPAMI 2024 | `Baseline` | **1 · 任务** — 将 VLN 从离散视点扩展到连续控制<br>**2 · 方法** — 构建逐步增长的拓扑规划表示<br>**3 · 亮点** — 结合长程规划与局部避障 |
| [**NavGPT: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models**](https://ojs.aaai.org/index.php/AAAI/article/view/28597) | AAAI 2024 | `Baseline` | **1 · 任务** — 利用 LLM 完成零样本指令导航<br>**2 · 方法** — 维护历史观察与可选前进方向<br>**3 · 亮点** — 显式输出子目标规划及纠错推理 |
| [**Uni-NaVid: A Video-based Vision-Language-Action Model for Unifying Embodied Navigation Tasks**](https://roboticsproceedings.org/rss21/p013.html) | RSS 2025 | `Baseline` | **1 · 任务** — 统一多种具身导航任务的 VLA 结构<br>**2 · 方法** — 输入自我中心视频与语言指令<br>**3 · 亮点** — 输出真实机器人可执行的底层动作 |
| [**CREStE: Scalable Mapless Navigation with Internet Scale Priors and Counterfactual Guidance**](https://roboticsproceedings.org/rss21/p136.html) | RSS 2025 | `Adjacent` | **1 · 任务** — 面向公里级室外无图导航<br>**2 · 方法** — 采用基础模型视觉先验与反事实引导<br>**3 · 亮点** — 在真实城市机器人上评测泛化 |
| [**OVRL-v2: A Simple State-of-the-Art Baseline for ImageNav and ObjectNav**](https://arxiv.org/abs/2303.07798) | arXiv 2023 | `Baseline` | **1 · 任务** — 提供通用视觉导航强基线<br>**2 · 方法** — 共同评估 ImageNav 与 ObjectNav<br>**3 · 亮点** — 适合作为感知表征与控制学习对照 |
| [**REVERIE: Remote Embodied Visual Referring Expression in Real Indoor Environments**](https://openaccess.thecvf.com/content_CVPR_2020/html/Qi_REVERIE_Remote_Embodied_Visual_Referring_Expression_in_Real_Indoor_Environments_CVPR_2020_paper.html) | CVPR 2020 | `Baseline` | **1 · 任务** — 连接目的地导航与目标实例定位<br>**2 · 方法** — 通过高层自然语言描述目标而非详细路径<br>**3 · 亮点** — 测试到达目标附近后是否准确识别对象 |
| [**Room-Across-Room: Multilingual Vision-and-Language Navigation with Dense Spatiotemporal Grounding**](https://aclanthology.org/2020.emnlp-main.356/) | EMNLP 2020 | `Benchmark` | **1 · 任务** — 将 VLN 扩展至英语、印地语和泰卢固语<br>**2 · 方法** — 提供词语到观察位姿的密集时空对应<br>**3 · 亮点** — 支持跨语言指令导航评测 |
| [**Beyond the Nav-Graph: Vision-and-Language Navigation in Continuous Environments**](https://arxiv.org/abs/2004.02857) | ECCV 2020 | `Baseline` | **1 · 任务** — 取消离散导航图和理想化边连接<br>**2 · 方法** — 需要连续三维移动与避障<br>**3 · 亮点** — 揭示指令推理与低层控制间的落差 |
| [**History to Future: Evolving Agent with Experience and Thought for Zero-shot Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Dai_History_to_Future_Evolving_Agent_with_Experience_and_Thought_for_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · 任务** — 将反馈式推理用于零样本连续 VLN<br>**2 · 方法** — 总结历史经验并预测未来地标<br>**3 · 亮点** — 根据过往失败反馈持续更新导航决策 |
| [**Waypoint Models for Instruction-Guided Navigation in Continuous Environments**](https://openaccess.thecvf.com/content/ICCV2021/papers/Krantz_Waypoint_Models_for_Instruction-Guided_Navigation_in_Continuous_Environments_ICCV_2021_paper.pdf) | ICCV 2021 | `Baseline` | **1 · 任务** — 在连续环境中预测可执行导航航点<br>**2 · 方法** — 支持全景观察与相对目标选择<br>**3 · 亮点** — 衔接语言推理和运动控制 |

<a id="sec-f"></a>

### 数据集、仿真器与评测基础设施 (5)

| 论文标题 | 发表位置 / 状态 | 研究关联 | 核心创新 · 3 点 |
| :--- | :--- | :--- | :--- |
| [**Habitat: A Platform for Embodied AI Research**](https://openaccess.thecvf.com/content_ICCV_2019/html/Savva_Habitat_A_Platform_for_Embodied_AI_Research_ICCV_2019_paper.html) | ICCV 2019 | `Benchmark` | **1 · 任务** — 提供高性能真实感具身仿真<br>**2 · 方法** — 支持 ObjectNav、PointNav 和传感器设置<br>**3 · 亮点** — 便于规范化导航训练与复现 |
| [**RoboTHOR: An Open Simulation-to-Real Embodied AI Platform**](https://openaccess.thecvf.com/content_CVPR_2020/html/Deitke_RoboTHOR_An_Open_Simulation-to-Real_Embodied_AI_Platform_CVPR_2020_paper.html) | CVPR 2020 | `Benchmark` | **1 · 任务** — 将仿真场景与对应真实环境配对<br>**2 · 方法** — 评估导航策略的仿真到现实偏差<br>**3 · 亮点** — 适用于实景主动感知评测 |
| [**Matterport3D: Learning from RGB-D Data in Indoor Environments**](https://gfx.cs.princeton.edu/pubs/Chang_2017_MLF/index.php) | 3DV 2017 | `Benchmark` | **1 · 任务** — 提供室内全景 RGB-D 场景<br>**2 · 方法** — 包含几何、相机位姿与语义标注<br>**3 · 亮点** — 是多种经典室内导航任务的数据基础 |
| [**Gibson Env: Real-World Perception for Embodied Agents**](https://openaccess.thecvf.com/content_cvpr_2018/html/Xia_Gibson_Env_Real-World_CVPR_2018_paper.html) | CVPR 2018 | `Benchmark` | **1 · 任务** — 基于真实场景重建构建具身学习环境<br>**2 · 方法** — 支持带物理交互的感知研究<br>**3 · 亮点** — 经典语义导航工作的常见测试基础 |
| [**Habitat 2.0: Training Home Assistants to Rearrange their Habitat**](https://proceedings.neurips.cc/paper_files/paper/2021/hash/021bbc7ee20b71134d53e20206bd6feb-Abstract.html) | NeurIPS 2021 | `Benchmark` | **1 · 任务** — 为 Habitat 增加可交互物理重排任务<br>**2 · 方法** — 连接导航与操作执行的场景和接口<br>**3 · 亮点** — 适合研究搜索完成后的具身交互 |

<a id="roadmap"></a>

## 研究路线与实验建议

**建议阅读顺序：** PONI → VLFM → WoMAP / Context-Nav → FUEL / STEM → UAV-ON → APEX / OctoMem-Agent → UAST → OpenFly / AirSim360。前半段学习主动搜索的目标函数，后半段研究空中三维感知和动作。

| 研究问题 | 必须控制的实验变量 | 推荐指标 |
| :--- | :--- | :--- |
| 主动导航真的优于普通导航吗？ | 相同感知模型、飞行速度、动作预算；仅替换航点策略 | SR、SPL、首次发现时间、覆盖效率 |
| 主动观察是否有价值？ | 固定相机 vs. 可转相机；前视 vs. 全景；允许 / 禁止机体转向 | 信息增益、目标首次可见步数、观测成本 |
| 三维运动是否必要？ | 只允许平面移动 vs. XYZ 三维平移；遮挡强弱分层 | SR、碰撞率、可见性、轨迹长度 |
| 搜索如何过渡到追踪？ | Search / Verify / Track / Reacquire 显式状态；目标消失与重现 | 搜索成功率、持续追踪率、重新捕获时延 |
| 世界模型如何帮助主动导航？ | 真实地图、局部地图、预测地图和空记忆对照 | 预测误差、SR、SPL、每次决策耗时 |

**结合全景 UAV 研究的独特切入点：** 固定机体航向下，只用 XYZ 平移改变观察位置；对比有限 FOV、全景 ERP、可控转向三种观测设定。要特别避免把“看见目标”直接等同于“主动搜索有效”，应评价目标发现时刻、信息增益、保持可见性及探索代价。

<a id="contributing"></a>

## 参与维护 · Contributing

建议提交：**准确论文标题、第一来源链接、真实发表位置/状态、Core/Adjacent/Baseline/Benchmark 标签，以及任务—方法—亮点三条简评**。投稿中、已录用、已发表必须明确区分。

当前收录是经筛选的研究清单，**不宣称覆盖全部论文**；对网页记载不明确者优先采用论文/出版方链接。`arXiv` 只表示预印本，不代表会议接收。

---

*仅供科研速览；正式写入论文参考文献前请再次核实作者、版本、venue、DOI。*
