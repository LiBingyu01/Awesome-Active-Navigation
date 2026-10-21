# Awesome Active Navigation · Paper Digest [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated research digest of **active perception, semantic exploration, object search, next-best-view planning, world models, and closed-loop aerial navigation** across ground and UAV platforms.

**Language:** English · [简体中文](README.zh-CN.md)

**75 papers & benchmarks · 6 research themes · 3 takeaways per paper · Updated: October 21, 2026**

## Contents

- [Editor’s Picks · Start Here](#featured)
- [Scope, Definitions & Inclusion Criteria](#scope)
- [Papers by Research Theme](#papers)
  - [Ground / General Active Semantic Navigation (25)](#sec-a)
  - [Aerial Active Search, ObjectNav & Perception (9)](#sec-b)
  - [Aerial VLN / VLA and Transfer Baselines (17)](#sec-c)
  - [Classical Frontiers, Next-Best-View & 3D Exploration (6)](#sec-d)
  - [General Navigation, VLN and VLA Baselines (13)](#sec-e)
  - [Datasets, Simulators & Evaluation Infrastructure (5)](#sec-f)
- [Research Roadmap & Experimental Design](#roadmap)
- [Contributing & Maintenance](#contributing)

<a id="featured"></a>

## Editor’s Picks · Start Here

An editorial reading path organized by relevance rather than publication rankings.

| Paper | Why read it? |
| :--- | :--- |
| [**UAST**](https://openaccess.thecvf.com/content/CVPR2026/html/Qin_UAST_Unified_Active_Search_and_Tracking_for_Arbitrary_Targets_with_CVPR_2026_paper.html) · CVPR 2026 | Closest link from active search to persistent UAV tracking. |
| [**APEX**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_APEX_A_Decoupled_Memory-based_Explorer_for_Asynchronous_Aerial_Object_Goal_CVPR_2026_paper.html) · CVPR 2026 | A strong aerial target-search pipeline with asynchronous memory and control. |
| [**OctoMem-Agent**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhou_Memory-Augmented_Scene_Understanding_and_Exploration_for_Open-World_Aerial_Object-Goal_Navigation_CVPR_2026_paper.html) · CVPR 2026 | Unknown 3D frontiers and instruction-conditioned octree memory. |
| [**STEM**](https://link.springer.com/article/10.1007/s10514-026-10247-6) · Autonomous Robots 2026 | Semantic information gain and 3D aerial viewpoint selection. |
| [**WoMAP**](https://proceedings.mlr.press/v305/yin25b.html) · CoRL 2025 | World-model-driven active localization and information-seeking behavior. |
| [**VLFM**](https://doi.org/10.1109/ICRA57147.2024.10610712) · ICRA 2024 | Practical training-free VLM frontier navigation on mobile robots. |
| [**PONI**](https://openaccess.thecvf.com/content/CVPR2022/html/Ramakrishnan_PONI_Potential_Functions_for_ObjectGoal_Navigation_With_Interaction-Free_Learning_CVPR_2022_paper.html) · CVPR 2022 | The foundational separation of where to search from how to move. |
| [**UAV-ON**](https://arxiv.org/abs/2508.00288) · arXiv 2025 | Task/data starting point for aerial ObjectNav without route instructions. |
| [**AerialVLN**](https://openaccess.thecvf.com/content/ICCV2023/html/Liu_AerialVLN_Vision-and-Language_Navigation_for_UAVs_ICCV_2023_paper.html) · ICCV 2023 | The canonical aerial instruction-following benchmark and a useful negative control. |
| [**OpenFly**](https://arxiv.org/abs/2502.18041) · arXiv 2025 | Scalable aerial VLN generation and continuous-action baseline. |

<a id="scope"></a>

## Scope, Definitions & Inclusion Criteria

**Strict Active Navigation** requires that motion or sensor-view selection be used explicitly to **gain information, reduce uncertainty, expand coverage, or verify target hypotheses**, rather than merely execute a known route.

**Core tasks:** ObjectNav, InstanceNav, active target search, Active SLAM, frontier exploration, NBV, information-gain planning, active tracking. **Comparators:** PointNav, ImageNav, ordinary VLN/VLA, classical route following.

**Relevance tags:** `Core` = explicit information-seeking or exploration; `Adjacent` = useful supporting method; `Baseline` = standard VLN/VLA/navigation; `Benchmark` = data, simulation, or evaluation resource.

We distinguish **Aerial ObjectNav (semantic target discovery without detailed route instructions)** from **Aerial VLN (language-instruction following)** to avoid task conflation.

<a id="papers"></a>

## Papers by Research Theme

<a id="sec-a"></a>

### Ground / General Active Semantic Navigation (25)

| Paper | Venue / Status | Research fit | 3 Key Takeaways |
| :--- | :--- | :--- | :--- |
| [**Object Goal Navigation using Goal-Oriented Semantic Exploration**](https://proceedings.neurips.cc/paper/2020/hash/2c75cf2681788adaca63aa95ae028b22-Abstract.html) | NeurIPS 2020 | `Core` | **1 · Task** — Object-category goal search in unseen interiors<br>**2 · Method** — Builds an episodic semantic map to drive exploration<br>**3 · Highlight** — Foundational modular semantic ObjectNav |
| [**PONI: Potential Functions for ObjectGoal Navigation With Interaction-Free Learning**](https://openaccess.thecvf.com/content/CVPR2022/html/Ramakrishnan_PONI_Potential_Functions_for_ObjectGoal_Navigation_With_Interaction-Free_Learning_CVPR_2022_paper.html) | CVPR 2022 | `Core` | **1 · Task** — Learns where to search separately from how to move<br>**2 · Method** — Predicts object and area potentials from partial maps<br>**3 · Highlight** — Trains exploration potentials without interactive rollouts |
| [**L3MVN: Leveraging Large Language Models for Visual Target Navigation**](https://arxiv.org/abs/2304.05501) | IROS 2023 | `Core` | **1 · Task** — Uses language commonsense to search for target objects<br>**2 · Method** — Ranks map frontiers using LLM-derived semantics<br>**3 · Highlight** — Studies zero-shot deployment and real-robot transfer |
| [**ESC: Exploration with Soft Commonsense Constraints for Zero-shot Object Navigation**](https://proceedings.mlr.press/v202/zhou23r.html) | ICML 2023 | `Core` | **1 · Task** — Searches for previously unseen object categories<br>**2 · Method** — Combines open-world grounding with commonsense constraints<br>**3 · Highlight** — Replaces task-specific policy training with zero-shot exploration |
| [**VLFM: Vision-Language Frontier Maps for Zero-Shot Semantic Navigation**](https://doi.org/10.1109/ICRA57147.2024.10610712) | ICRA 2024 | `Core` | **1 · Task** — Selects promising frontiers for semantic targets<br>**2 · Method** — Builds VLM-conditioned value maps over free space<br>**3 · Highlight** — Demonstrates transfer to the physical Spot robot |
| [**VoroNav: Voronoi-based Zero-shot Object Navigation with Large Language Model**](https://proceedings.mlr.press/v235/wu24u.html) | ICML 2024 | `Core` | **1 · Task** — Targets efficient zero-shot object search<br>**2 · Method** — Builds reduced Voronoi graphs and path descriptions<br>**3 · Highlight** — Uses LLM reasoning to choose exploration waypoints |
| [**OpenFMNav: Towards Open-Set Zero-Shot Object Navigation via Vision-Language Foundation Models**](https://aclanthology.org/2024.findings-naacl.24/) | Findings of NAACL 2024 | `Core` | **1 · Task** — Interprets open-set language-specified object goals<br>**2 · Method** — Builds a versatile semantic score map with foundation models<br>**3 · Highlight** — Performs language-guided exploration and exploitation |
| [**SG-Nav: Online 3D Scene Graph Prompting for LLM-based Zero-shot Object Navigation**](https://arxiv.org/abs/2410.08189) | NeurIPS 2024 | `Core` | **1 · Task** — Maintains a structured scene representation during search<br>**2 · Method** — Prompts an LLM with an online 3D scene graph<br>**3 · Highlight** — Uses semantic relations and revisitation for target discovery |
| [**Instance-aware Exploration-Verification-Exploitation for Instance ImageGoal Navigation**](https://openaccess.thecvf.com/content/CVPR2024/html/Lei_Instance-aware_Exploration-Verification-Exploitation_for_Instance_ImageGoal_Navigation_CVPR_2024_paper.html) | CVPR 2024 | `Core` | **1 · Task** — Searches for a particular instance rather than a category<br>**2 · Method** — Switches among exploration verification and exploitation<br>**3 · Highlight** — Uses approach-for-confirmation to reject similar distractors |
| [**MOPA: Modular Object Navigation With PointGoal Agents**](https://openaccess.thecvf.com/content/WACV2024/html/Raychaudhuri_MOPA_Modular_Object_Navigation_With_PointGoal_Agents_WACV_2024_paper.html) | WACV 2024 | `Adjacent` | **1 · Task** — Decomposes ObjectNav into detection mapping exploration and motion<br>**2 · Method** — Reuses trained PointNav policies instead of retraining navigation<br>**3 · Highlight** — Compares exploration heuristics under a shared framework |
| [**Imagine Before Go: Self-Supervised Generative Map for Object Goal Navigation**](https://openaccess.thecvf.com/content/CVPR2024/html/Zhang_Imagine_Before_Go_Self-Supervised_Generative_Map_for_Object_Goal_Navigation_CVPR_2024_paper.html) | CVPR 2024 | `Core` | **1 · Task** — Predicts unobserved scene information for ObjectNav<br>**2 · Method** — Uses a self-supervised generative map prior<br>**3 · Highlight** — Guides search before complete observation is available |
| [**ForesightNav: Learning Scene Imagination for Efficient Exploration**](https://openaccess.thecvf.com/content/CVPR2025W/OpenSUN3D/html/Shah_ForesightNav_Learning_Scene_Imagination_for_Efficient_Exploration_CVPRW_2025_paper.html) | CVPR Workshops 2025 | `Core` | **1 · Task** — Imagines occupancy and semantics behind observed regions<br>**2 · Method** — Selects long-term exploration goals from predicted layouts<br>**3 · Highlight** — Tests effects on PointNav and ObjectNav |
| [**Active Perception Meets Rule-Guided RL: A Two-Phase Approach for Precise Object Navigation in Complex Environments**](https://openaccess.thecvf.com/content/ICCV2025/html/Qin_Active_Perception_Meets_Rule-Guided_RL_A_Two-Phase_Approach_for_Precise_ICCV_2025_paper.html) | ICCV 2025 | `Core` | **1 · Task** — Addresses both long-range search and final positioning<br>**2 · Method** — Combines rule-guided RL exploration with active perception<br>**3 · Highlight** — Targets precise arrival for downstream manipulation |
| [**CogNav: Cognitive Process Modeling for Object Goal Navigation with LLMs**](https://openaccess.thecvf.com/content/ICCV2025/html/Cao_CogNav_Cognitive_Process_Modeling_for_Object_Goal_Navigation_with_LLMs_ICCV_2025_paper.html) | ICCV 2025 | `Core` | **1 · Task** — Represents object search as explicit cognitive states<br>**2 · Method** — Uses a heterogeneous map and LLM-controlled state transitions<br>**3 · Highlight** — Supports interpretable exploration and identification |
| [**Function-centric Bayesian Network for Zero-Shot Object Goal Navigation**](https://openaccess.thecvf.com/content/ICCV2025/html/Zhang_Function-centric_Bayesian_Network_for_Zero-Shot_Object_Goal_Navigation_ICCV_2025_paper.html) | ICCV 2025 | `Core` | **1 · Task** — Infers hidden targets using object functions and contexts<br>**2 · Method** — Builds a Bayesian network over objects scenes and functions<br>**3 · Highlight** — Selects waypoints from posterior target-location probabilities |
| [**Context-Nav: Context-Driven Exploration and Viewpoint-Aware 3D Spatial Reasoning for Instance Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Jang_Context-Nav_Context-Driven_Exploration_and_Viewpoint-Aware_3D_Spatial_Reasoning_for_Instance_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · Task** — Locates a text-described instance among similar objects<br>**2 · Method** — Ranks exploration frontiers from full descriptive context<br>**3 · Highlight** — Verifies spatial relationships from plausible viewpoints |
| [**TrajRAG: Retrieving Geometric-Semantic Experience for Zero-Shot Object Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Wang_TrajRAG_Retrieving_Geometric-Semantic_Experience_for_Zero-Shot_Object_Navigation_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · Task** — Reuses navigation experience from prior episodes<br>**2 · Method** — Encodes trajectories as compact topological-polar memories<br>**3 · Highlight** — Retrieves relevant experiences for frontier selection |
| [**UniGoal: Towards Universal Zero-shot Goal-oriented Navigation**](https://openaccess.thecvf.com/content/CVPR2025/papers/Yin_UniGoal_Towards_Universal_Zero-shot_Goal-oriented_Navigation_CVPR_2025_paper.pdf) | CVPR 2025 | `Core` | **1 · Task** — Unifies category image and language navigation goals<br>**2 · Method** — Matches goal graphs against an online scene graph<br>**3 · Highlight** — Switches exploration strategies by match completeness |
| [**Multi-Scale Gaussian-Language Map for Zero-shot Embodied Navigation and Reasoning**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_Multi-Scale_Gaussian-Language_Map_for_Zero-shot_Embodied_Navigation_and_Reasoning_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · Task** — Builds navigable memory from explicit 3D geometry and language<br>**2 · Method** — Stores instance and region descriptions beside Gaussians<br>**3 · Highlight** — Supports zero-shot goal localization and spatial reasoning |
| [**WoMAP: World Models For Embodied Open-Vocabulary Object Localization**](https://proceedings.mlr.press/v305/yin25b.html) | CoRL 2025 | `Core` | **1 · Task** — Trains active object localization under partial observability<br>**2 · Method** — Combines 3DGS-based data synthesis and detector rewards<br>**3 · Highlight** — Uses a latent world model to ground action proposals |
| [**InstructNav: Zero-shot System for Generic Instruction Navigation in Unexplored Environment**](https://arxiv.org/abs/2406.04882) | CoRL 2024 | `Adjacent` | **1 · Task** — Handles multiple language-driven navigation goal types<br>**2 · Method** — Combines dynamic navigation reasoning with value maps<br>**3 · Highlight** — Transfers zero-shot to ObjectNav and continuous VLN |
| [**GOAT-Bench: A Benchmark for Multi-Modal Lifelong Navigation**](https://openaccess.thecvf.com/content/CVPR2024/html/Khanna_GOAT-Bench_A_Benchmark_for_Multi-Modal_Lifelong_Navigation_CVPR_2024_paper.html) | CVPR 2024 | `Benchmark` | **1 · Task** — Defines sequential multi-goal category image and text navigation<br>**2 · Method** — Measures reuse of memory across a continuing episode<br>**3 · Highlight** — Connects active exploration with lifelong semantic recall |
| [**DARE: Diffusion Policy for Autonomous Robot Exploration**](https://doi.org/10.1109/ICRA55743.2025.11128196) | ICRA 2025 | `Core` | **1 · Task** — Generates exploration trajectories in unknown spaces<br>**2 · Method** — Learns long-horizon plans with diffusion from experts<br>**3 · Highlight** — Reasons about unobserved layouts from partial maps |
| [**CogniPlan: Uncertainty-Guided Path Planning with Conditional Generative Layout Prediction**](https://proceedings.mlr.press/v305/wang25d.html) | CoRL 2025 | `Core` | **1 · Task** — Plans routes despite unknown environmental structure<br>**2 · Method** — Uses generative layout completion to reason about uncertainty<br>**3 · Highlight** — Connects uncertainty modeling to action-level planning |
| [**SOON: Scenario Oriented Object Navigation With Graph-Based Exploration**](https://openaccess.thecvf.com/content/CVPR2021/html/Zhu_SOON_Scenario_Oriented_Object_Navigation_With_Graph-Based_Exploration_CVPR_2021_paper.html) | CVPR 2021 | `Core` | **1 · Task** — Defines free-start object search from scene descriptions<br>**2 · Method** — Uses graph-based exploration for long-horizon target finding<br>**3 · Highlight** — Pairs navigation with explicit final object localization |

<a id="sec-b"></a>

### Aerial Active Search, ObjectNav & Perception (9)

| Paper | Venue / Status | Research fit | 3 Key Takeaways |
| :--- | :--- | :--- | :--- |
| [**UAV-ON: A Benchmark for Open-World Object Goal Navigation with Aerial Agents**](https://arxiv.org/abs/2508.00288) | arXiv 2025 | `Benchmark` | **1 · Task** — Defines aerial ObjectNav without detailed route instructions<br>**2 · Method** — Provides open-world UAV scenes and instance targets<br>**3 · Highlight** — Exposes exploration and semantic-grounding difficulty |
| [**APEX: A Decoupled Memory-based Explorer for Asynchronous Aerial Object Goal Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_APEX_A_Decoupled_Memory-based_Explorer_for_Asynchronous_Aerial_Object_Goal_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · Task** — Searches objects actively in complex aerial scenes<br>**2 · Method** — Couples semantic 3D maps with RL action decisions<br>**3 · Highlight** — Runs target grounding asynchronously to reduce VLM delay |
| [**Memory-Augmented Scene Understanding and Exploration for Open-World Aerial Object-Goal Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhou_Memory-Augmented_Scene_Understanding_and_Exploration_for_Open-World_Aerial_Object-Goal_Navigation_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · Task** — Performs instruction-guided exploration for aerial ObjectNav<br>**2 · Method** — Builds adaptive octree memory of observed and unseen 3D space<br>**3 · Highlight** — Queries memory tokens for target-driven search |
| [**STEM: Semantic target search and exploration using MAVs in cluttered environments**](https://link.springer.com/article/10.1007/s10514-026-10247-6) | Autonomous Robots 2026 | `Core` | **1 · Task** — Finds target objects with micro aerial vehicles<br>**2 · Method** — Combines semantic relevance with coverage-based exploration<br>**3 · Highlight** — Prioritizes promising 3D viewpoints in cluttered spaces |
| [**UAST: Unified Active Search and Tracking for Arbitrary Targets with UAVs**](https://openaccess.thecvf.com/content/CVPR2026/html/Qin_UAST_Unified_Active_Search_and_Tracking_for_Arbitrary_Targets_with_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · Task** — Unifies target acquisition and sustained aerial tracking<br>**2 · Method** — Uses RGB-D perception and switchable search-recovery logic<br>**3 · Highlight** — Couples target visibility with flight trajectory control |
| [**Dual-Layer Semantic-Spatial Belief Mapping for Aerial Object Goal Navigation**](https://arxiv.org/abs/2609.08164) | arXiv 2026 | `Core` | **1 · Task** — Maintains persistent uncertainty-aware target beliefs<br>**2 · Method** — Separates scene intuition from verified object evidence<br>**3 · Highlight** — Stabilizes regional exploration and candidate confirmation |
| [**Reinforcement Learning for Active Perception in Autonomous Navigation**](https://arxiv.org/abs/2602.01266) | arXiv 2026 | `Core` | **1 · Task** — Jointly controls robot motion and an actuated camera<br>**2 · Method** — Adds voxel information gain to navigation rewards<br>**3 · Highlight** — Encourages safer aerial navigation through exploratory sensing |
| [**Parse, Search, and Confirmation: Training-Free Aerial Vision-and-Dialog Navigation with Chain-of-Thought Reasoning and Structured Spatial Memory**](https://openaccess.thecvf.com/content/CVPR2026/html/Qi_Parse_Search_and_Confirmation_Training-Free_Aerial_Vision-and-Dialog_Navigation_with_Chain-of-Thought_CVPR_2026_paper.html) | CVPR 2026 | `Core` | **1 · Task** — Searches and verifies landmarks from aerial dialogue<br>**2 · Method** — Uses parse-search-confirm reasoning stages<br>**3 · Highlight** — Keeps structured spatial memory without task training |
| [**Maximizing aerial detection of organic objects in non-exhaustively searchable survey area**](https://openaccess.thecvf.com/content/CVPR2025W/V4A/html/Niaraki_Maximizing_aerial_detection_of_organic_objects_in_non-exhaustively_searchable_survey_CVPRW_2025_paper.html) | CVPR Workshops 2025 | `Core` | **1 · Task** — Addresses target discovery when full coverage is infeasible<br>**2 · Method** — Plans 3D search paths from detections and wind conditions<br>**3 · Highlight** — Connects aerial sensing value with limited flight resources |

<a id="sec-c"></a>

### Aerial VLN / VLA and Transfer Baselines (17)

| Paper | Venue / Status | Research fit | 3 Key Takeaways |
| :--- | :--- | :--- | :--- |
| [**AerialVLN: Vision-and-Language Navigation for UAVs**](https://openaccess.thecvf.com/content/ICCV2023/html/Liu_AerialVLN_Vision-and-Language_Navigation_for_UAVs_ICCV_2023_paper.html) | ICCV 2023 | `Baseline` | **1 · Task** — Introduces a continuous aerial VLN benchmark<br>**2 · Method** — Simulates 3D city scenes and language instructions<br>**3 · Highlight** — Highlights altitude and 3D action-space challenges |
| [**Aerial Vision-and-Dialog Navigation**](https://arxiv.org/abs/2205.12219) | arXiv 2022 | `Baseline` | **1 · Task** — Studies aerial navigation assisted by human dialogue<br>**2 · Method** — Records navigation trajectories and human attention<br>**3 · Highlight** — Introduces history-dependent waypoint prediction |
| [**Towards Realistic UAV Vision-Language Navigation: Platform, Benchmark, and Methodology**](https://arxiv.org/abs/2410.07087) | arXiv 2024 | `Baseline` | **1 · Task** — Builds realistic UAV flight simulation and TravelUAV<br>**2 · Method** — Introduces assistant-guided UAV search settings<br>**3 · Highlight** — Connects MLLM reasoning with hierarchical trajectory control |
| [**OpenFly: A Versatile Toolchain and Large-scale Benchmark for Aerial Vision-Language Navigation**](https://arxiv.org/abs/2502.18041) | arXiv 2025 | `Benchmark` | **1 · Task** — Offers a scalable aerial VLN data-generation toolchain<br>**2 · Method** — Builds trajectories across multiple outdoor renderers<br>**3 · Highlight** — Provides a keyframe-aware navigation baseline |
| [**CityNav: A Large-Scale Dataset for Real-World Aerial Navigation**](https://openaccess.thecvf.com/content/ICCV2025/html/Lee_CityNav_A_Large-Scale_Dataset_for_Real-World_Aerial_Navigation_ICCV_2025_paper.html) | ICCV 2025 | `Benchmark` | **1 · Task** — Benchmarks aerial VLN over real city geometry<br>**2 · Method** — Pairs flight trajectories with detailed target descriptions<br>**3 · Highlight** — Studies geographic semantic-map assistance |
| [**CityNavAgent: Aerial Vision-and-Language Navigation with Hierarchical Semantic Planning and Global Memory**](https://aclanthology.org/2025.acl-long.1511/) | ACL 2025 | `Adjacent` | **1 · Task** — Splits long aerial routes into semantic subgoals<br>**2 · Method** — Maintains a global topological memory of experience<br>**3 · Highlight** — Uses LLM reasoning for progressive waypoint selection |
| [**UAV-Flow Colosseo: A Real-World Benchmark for Flying-on-a-Word UAV Imitation Learning**](https://arxiv.org/abs/2505.15725) | arXiv 2025 | `Benchmark` | **1 · Task** — Focuses on fine-grained language-conditioned UAV motion<br>**2 · Method** — Records real pilot trajectories paired with atomic commands<br>**3 · Highlight** — Provides low-level control evaluation beyond high-level VLN |
| [**HTNav: A Hybrid Navigation Framework with Tiered Structure for Urban Aerial Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Fan_HTNav_A_Hybrid_Navigation_Framework_with_Tiered_Structure_for_Urban_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · Task** — Targets generalizable long-range aerial VLN<br>**2 · Method** — Combines staged imitation and reinforcement learning<br>**3 · Highlight** — Improves exploration in urban spatial layouts |
| [**LookasideVLN: Direction-Aware Aerial Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Ning_LookasideVLN_Direction-Aware_Aerial_Vision-and-Language_Navigation_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · Task** — Explains directional words relative to UAV viewpoints<br>**2 · Method** — Constructs an egocentric directional landmark graph<br>**3 · Highlight** — Uses historical spatial landmark knowledge for route planning |
| [**AerialVLA: A Vision-Language-Action Model for UAV Navigation via Minimalist End-to-End Control**](https://arxiv.org/abs/2603.14363) | arXiv 2026 | `Baseline` | **1 · Task** — Maps language and onboard vision to continuous actions<br>**2 · Method** — Uses dual-view perception and sensor-only direction cues<br>**3 · Highlight** — Studies fine-grained navigation and landing |
| [**LongFly: Long-Horizon UAV Vision-and-Language Navigation with Spatiotemporal Context Integration**](https://arxiv.org/abs/2512.22010) | arXiv 2025 | `Adjacent` | **1 · Task** — Models long-horizon aerial instruction execution<br>**2 · Method** — Compresses historical frames into spatial-temporal context<br>**3 · Highlight** — Fuses trajectory history with current observations |
| [**Fly0: Decoupling Semantic Grounding from Geometric Planning for Zero-Shot Aerial Navigation**](https://arxiv.org/abs/2602.15875) | arXiv 2026 | `Adjacent` | **1 · Task** — Separates VLM semantic grounding from safe control<br>**2 · Method** — Projects target pixels into 3D coordinates using depth<br>**3 · Highlight** — Uses a geometric planner to avoid continuous VLM calls |
| [**OnFly: Onboard Zero-Shot Aerial Vision-Language Navigation toward Safety and Efficiency**](https://arxiv.org/abs/2603.10682) | arXiv 2026 | `Adjacent` | **1 · Task** — Enables fully onboard aerial instruction navigation<br>**2 · Method** — Decouples target proposal and progress monitoring agents<br>**3 · Highlight** — Uses semantic-geometric verification and safe planning |
| [**RecoverFly: A Failure-Aware Reinforcement Learning Post-Training Framework for Aerial Vision-Language Navigation**](https://arxiv.org/abs/2608.09467) | arXiv 2026 | `Adjacent` | **1 · Task** — Targets recovery from failed aerial VLN rollouts<br>**2 · Method** — Replays hard failures during RL post-training<br>**3 · Highlight** — Improves closed-loop robustness of end-to-end UAV VLA |
| [**Beyond Matching to Tiles: Bridging Unaligned Aerial and Satellite Views for Vision-Only UAV Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Liu_Beyond_Matching_to_Tiles_Bridging_Unaligned_Aerial_and_Satellite_Views_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · Task** — Navigates with aerial-to-satellite visual correspondence<br>**2 · Method** — Handles geometric mismatch between onboard and overhead views<br>**3 · Highlight** — Supports vision-only localization under limited GNSS |
| [**Is your VLM Sky-Ready? A Comprehensive Spatial Intelligence Benchmark for UAV Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Zhang_Is_your_VLM_Sky-Ready_A_Comprehensive_Spatial_Intelligence_Benchmark_for_CVPR_2026_paper.html) | CVPR 2026 | `Benchmark` | **1 · Task** — Tests spatial reasoning relevant to UAV flight<br>**2 · Method** — Covers direction distance altitude and landing safety<br>**3 · Highlight** — Identifies limits of VLMs as navigation perception engines |
| [**AirSim360: A Panoramic Simulation Platform within Drone View**](https://openaccess.thecvf.com/content/CVPR2026/html/Ge_AirSim360_A_Panoramic_Simulation_Platform_within_Drone_View_CVPR_2026_paper.html) | CVPR 2026 | `Benchmark` | **1 · Task** — Simulates omnidirectional sensing from moving drones<br>**2 · Method** — Provides panoramic geometric and semantic labels<br>**3 · Highlight** — Supports automated aerial trajectory and navigation data |

<a id="sec-d"></a>

### Classical Frontiers, Next-Best-View & 3D Exploration (6)

| Paper | Venue / Status | Research fit | 3 Key Takeaways |
| :--- | :--- | :--- | :--- |
| [**A Frontier-Based Approach for Autonomous Exploration**](https://doi.org/10.1109/CIRA.1997.613851) | CIRA 1997 | `Core` | **1 · Task** — Introduces frontier boundaries as exploration targets<br>**2 · Method** — Chooses reachable unknown-known interfaces<br>**3 · Highlight** — Establishes a baseline for modern active exploration |
| [**Receding Horizon Next-Best-View Planner for 3D Exploration**](https://doi.org/10.1109/ICRA.2016.7487281) | ICRA 2016 | `Core` | **1 · Task** — Selects camera poses that reveal unknown 3D space<br>**2 · Method** — Optimizes information gain over a sampled planning tree<br>**3 · Highlight** — Executes the first edge and replans onboard a UAV |
| [**FUEL: Fast UAV Exploration using Incremental Frontier Structure and Hierarchical Planning**](https://arxiv.org/abs/2010.11561) | IEEE RA-L 2021 | `Core` | **1 · Task** — Optimizes autonomous coverage of unknown UAV environments<br>**2 · Method** — Updates frontiers incrementally with hierarchical planning<br>**3 · Highlight** — Produces efficient minimum-time exploration trajectories |
| [**TARE: A Hierarchical Framework for Efficiently Exploring Complex 3D Environments**](https://www.roboticsproceedings.org/rss17/p018.html) | RSS 2021 | `Core` | **1 · Task** — Explores complex unknown 3D environments<br>**2 · Method** — Uses dense local plans and sparse global coverage<br>**3 · Highlight** — Evaluated on ground and aerial platforms |
| [**FAEL: Fast Autonomous Exploration for Large-scale Environments With a Mobile Robot**](https://doi.org/10.1109/LRA.2023.3236573) | IEEE RA-L 2023 | `Core` | **1 · Task** — Accelerates exploration over large environments<br>**2 · Method** — Builds efficient candidate selection and path planning<br>**3 · Highlight** — Provides a ground-robot baseline for aerial comparisons |
| [**ARiADNE: A Reinforcement Learning Approach Using Attention-Based Deep Networks for Exploration**](https://doi.org/10.1109/ICRA48891.2023.10160565) | ICRA 2023 | `Core` | **1 · Task** — Treats unknown-space exploration as learned decision-making<br>**2 · Method** — Uses attention-based networks for next-goal prediction<br>**3 · Highlight** — Motivates diffusion-based exploration successors |

<a id="sec-e"></a>

### General Navigation, VLN and VLA Baselines (13)

| Paper | Venue / Status | Research fit | 3 Key Takeaways |
| :--- | :--- | :--- | :--- |
| [**Vision-and-Language Navigation: Interpreting Visually-Grounded Navigation Instructions in Real Environments**](https://openaccess.thecvf.com/content_cvpr_2018/html/Anderson_Vision-and-Language_Navigation_Interpreting_CVPR_2018_paper.html) | CVPR 2018 | `Baseline` | **1 · Task** — Introduces the Room-to-Room language navigation task<br>**2 · Method** — Pairs human descriptions with real indoor panoramas<br>**3 · Highlight** — Defines standard success metrics for instruction following |
| [**Reinforced Cross-Modal Matching and Self-Supervised Imitation Learning for Vision-Language Navigation**](https://openaccess.thecvf.com/content_CVPR_2019/html/Wang_Reinforced_Cross-Modal_Matching_and_Self-Supervised_Imitation_Learning_for_Vision-Language_Navigation_CVPR_2019_paper.html) | CVPR 2019 | `Baseline` | **1 · Task** — Aligns instructions with trajectories and visual observations<br>**2 · Method** — Uses cross-modal reward and self-imitation learning<br>**3 · Highlight** — Improves generalization to unseen navigation scenes |
| [**Think Global, Act Local: Dual-Scale Graph Transformer for Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2022/html/Chen_Think_Global_Act_Local_Dual-Scale_Graph_Transformer_for_Vision-and-Language_Navigation_CVPR_2022_paper.html) | CVPR 2022 | `Baseline` | **1 · Task** — Combines local language grounding with global planning<br>**2 · Method** — Builds a topological navigation graph online<br>**3 · Highlight** — Offers a standard map-based VLN policy comparison |
| [**ETPNav: Evolving Topological Planning for Vision-Language Navigation in Continuous Environments**](https://github.com/ifundo/ETPNav) | IEEE TPAMI 2024 | `Baseline` | **1 · Task** — Moves VLN from discrete graphs to continuous control<br>**2 · Method** — Builds evolving topological planning representations<br>**3 · Highlight** — Combines long-range planning and obstacle avoidance |
| [**NavGPT: Explicit Reasoning in Vision-and-Language Navigation with Large Language Models**](https://ojs.aaai.org/index.php/AAAI/article/view/28597) | AAAI 2024 | `Baseline` | **1 · Task** — Uses LLM reasoning for zero-shot instruction following<br>**2 · Method** — Maintains navigation history and possible directions<br>**3 · Highlight** — Makes subgoal planning and corrections explicit |
| [**Uni-NaVid: A Video-based Vision-Language-Action Model for Unifying Embodied Navigation Tasks**](https://roboticsproceedings.org/rss21/p013.html) | RSS 2025 | `Baseline` | **1 · Task** — Unifies multiple navigation tasks under one VLA policy<br>**2 · Method** — Consumes egocentric video and language instructions<br>**3 · Highlight** — Predicts low-level robotic actions for real-world tasks |
| [**CREStE: Scalable Mapless Navigation with Internet Scale Priors and Counterfactual Guidance**](https://roboticsproceedings.org/rss21/p136.html) | RSS 2025 | `Adjacent` | **1 · Task** — Targets kilometer-scale outdoor robot mobility<br>**2 · Method** — Uses foundation-model perception and counterfactual guidance<br>**3 · Highlight** — Evaluates generalization on physical urban robots |
| [**OVRL-v2: A Simple State-of-the-Art Baseline for ImageNav and ObjectNav**](https://arxiv.org/abs/2303.07798) | arXiv 2023 | `Baseline` | **1 · Task** — Provides a strong general visual navigation policy<br>**2 · Method** — Tests ImageNav and ObjectNav in a common framework<br>**3 · Highlight** — Useful as a representation-learning control baseline |
| [**REVERIE: Remote Embodied Visual Referring Expression in Real Indoor Environments**](https://openaccess.thecvf.com/content_CVPR_2020/html/Qi_REVERIE_Remote_Embodied_Visual_Referring_Expression_in_Real_Indoor_Environments_CVPR_2020_paper.html) | CVPR 2020 | `Baseline` | **1 · Task** — Combines goal-directed navigation with object grounding<br>**2 · Method** — Uses high-level natural language rather than full routes<br>**3 · Highlight** — Benchmarks identification after arriving near a target |
| [**Room-Across-Room: Multilingual Vision-and-Language Navigation with Dense Spatiotemporal Grounding**](https://aclanthology.org/2020.emnlp-main.356/) | EMNLP 2020 | `Benchmark` | **1 · Task** — Expands VLN to English Hindi and Telugu directions<br>**2 · Method** — Adds dense word-to-pose temporal grounding<br>**3 · Highlight** — Supports more realistic cross-lingual instruction comparison |
| [**Beyond the Nav-Graph: Vision-and-Language Navigation in Continuous Environments**](https://arxiv.org/abs/2004.02857) | ECCV 2020 | `Baseline` | **1 · Task** — Removes oracle graph edges from language navigation<br>**2 · Method** — Requires continuous 3D locomotion and obstacle handling<br>**3 · Highlight** — Exposes the challenge of low-level action execution |
| [**History to Future: Evolving Agent with Experience and Thought for Zero-shot Vision-and-Language Navigation**](https://openaccess.thecvf.com/content/CVPR2026/html/Dai_History_to_Future_Evolving_Agent_with_Experience_and_Thought_for_CVPR_2026_paper.html) | CVPR 2026 | `Adjacent` | **1 · Task** — Uses reflective reasoning in zero-shot continuous VLN<br>**2 · Method** — Summarizes prior experience and predicts future landmarks<br>**3 · Highlight** — Updates navigation decisions with history-based feedback |
| [**Waypoint Models for Instruction-Guided Navigation in Continuous Environments**](https://openaccess.thecvf.com/content/ICCV2021/papers/Krantz_Waypoint_Models_for_Instruction-Guided_Navigation_in_Continuous_Environments_ICCV_2021_paper.pdf) | ICCV 2021 | `Baseline` | **1 · Task** — Predicts navigation waypoints in continuous scenes<br>**2 · Method** — Supports panoramic sensing and relative point selection<br>**3 · Highlight** — Connects high-level language following to motion execution |

<a id="sec-f"></a>

### Datasets, Simulators & Evaluation Infrastructure (5)

| Paper | Venue / Status | Research fit | 3 Key Takeaways |
| :--- | :--- | :--- | :--- |
| [**Habitat: A Platform for Embodied AI Research**](https://openaccess.thecvf.com/content_ICCV_2019/html/Savva_Habitat_A_Platform_for_Embodied_AI_Research_ICCV_2019_paper.html) | ICCV 2019 | `Benchmark` | **1 · Task** — Provides fast photorealistic embodied simulation<br>**2 · Method** — Supports ObjectNav PointNav and sensor configuration<br>**3 · Highlight** — Standardizes reproducible visual navigation training |
| [**RoboTHOR: An Open Simulation-to-Real Embodied AI Platform**](https://openaccess.thecvf.com/content_CVPR_2020/html/Deitke_RoboTHOR_An_Open_Simulation-to-Real_Embodied_AI_Platform_CVPR_2020_paper.html) | CVPR 2020 | `Benchmark` | **1 · Task** — Pairs simulation environments with real counterparts<br>**2 · Method** — Measures navigation policy sim-to-real gaps<br>**3 · Highlight** — Useful for physically grounded active-perception tests |
| [**Matterport3D: Learning from RGB-D Data in Indoor Environments**](https://gfx.cs.princeton.edu/pubs/Chang_2017_MLF/index.php) | 3DV 2017 | `Benchmark` | **1 · Task** — Provides indoor panoramic RGB-D scenes<br>**2 · Method** — Includes geometry camera poses and semantic labels<br>**3 · Highlight** — Underlies several indoor navigation benchmarks |
| [**Gibson Env: Real-World Perception for Embodied Agents**](https://openaccess.thecvf.com/content_cvpr_2018/html/Xia_Gibson_Env_Real-World_CVPR_2018_paper.html) | CVPR 2018 | `Benchmark` | **1 · Task** — Builds embodied learning around reconstructed real environments<br>**2 · Method** — Supports physical-simulation visual perception studies<br>**3 · Highlight** — Common evaluation context for early semantic navigation |
| [**Habitat 2.0: Training Home Assistants to Rearrange their Habitat**](https://proceedings.neurips.cc/paper_files/paper/2021/hash/021bbc7ee20b71134d53e20206bd6feb-Abstract.html) | NeurIPS 2021 | `Benchmark` | **1 · Task** — Adds interactive physical rearrangement to Habitat<br>**2 · Method** — Enables navigation alongside manipulation actions<br>**3 · Highlight** — Useful when a search task requires eventual interaction |

<a id="roadmap"></a>

## Research Roadmap & Experimental Design

**Suggested reading order:** PONI → VLFM → WoMAP / Context-Nav → FUEL / STEM → UAV-ON → APEX / OctoMem-Agent → UAST → OpenFly / AirSim360. Read search objectives first, then 3D aerial embodiment.

| Research question | Controlled comparison | Suggested metrics |
| :--- | :--- | :--- |
| Is active navigation better than ordinary navigation? | Hold perception, speed, and action budget fixed; change only waypoint policy | SR, SPL, time-to-first-detection, exploration efficiency |
| Does active observation help? | Fixed vs. movable camera; narrow FOV vs. panoramic; heading control on/off | Information gain, target visibility, sensing cost |
| Does 3D mobility matter? | Planar moves vs. XYZ translation; varying occlusion difficulty | SR, collision rate, path length, visibility |
| How should search transition to tracking? | Explicit Search / Verify / Track / Reacquire states | Discovery SR, track persistence, reacquisition delay |
| Do world models improve exploration? | Oracle / partial / imagined / memory-free maps | Prediction accuracy, SR, SPL, planning runtime |

**Aerial panorama research opportunity:** Keep UAV heading fixed and let XYZ translation change the view, then contrast front-facing, ERP 360°, and yaw-enabled agents. Evaluate actual discovery time and information gain, not mere target visibility.

<a id="contributing"></a>

## Contributing & Maintenance

Propose an entry with **an exact title, primary paper link, verified venue/status, relevance tag, and three concise task–method–highlight takeaways**. Clearly separate submitted, accepted, published, and preprint status.

This is a **curated, non-exhaustive** digest. An `arXiv` label means preprint availability, **not** acceptance at a conference.

---

*Curated for research use; bibliographic status should be rechecked before citing in a submitted paper.*
