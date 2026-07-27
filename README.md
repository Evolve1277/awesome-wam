# Awesome WAM

A continuously updated index of **World Action Models (WAMs)** for embodied robot control.

In this index, a WAM is a model where world prediction, video generation, future-state modeling, or joint world-action learning is a direct part of action prediction, planning, or closed-loop control.

[Quick Comparison](#quick-comparison) | [Method Records](#method-records) | [Benchmark Notes](#benchmark-notes) | [Inclusion Principles](#inclusion-principles)

> [!IMPORTANT]
> All figures below are reported by the original authors or official project materials. Datasets, embodiments, action spaces, evaluation protocols, rollout budgets, model sizes, and training recipes differ across papers. This is a source-linked reference index, not a normalized leaderboard.

## Quick Comparison

`--` means that the official source did not report a score on that benchmark. RoboTwin labels are preserved exactly as reported; `Easy/Hard` and `clean/randomized` are not interchangeable protocols. RoboDojo values are a live-leaderboard snapshot dated 2026-07-27; its `Score` and binary `SR` are both retained.

| Method | Year | RoboTwin 2.0 | RoboDojo | Other key reported result(s) | Links |
| --- | ---: | --- | --- | --- | --- |
| [Action Images](https://arxiv.org/abs/2604.06168) | 2026 | -- | -- | RLBench zero-shot SR: **38.75%**; real xArm zero-shot average SR: **26.0%**. | [paper](https://arxiv.org/abs/2604.06168) / [project](https://actionimages.github.io/) / [code](https://github.com/UMass-Embodied-AGI/ActionImages) |
| [AIM](https://arxiv.org/abs/2604.11135) | 2026 | Easy: **94.0%**; Hard: **92.1%** | -- | Reported with 30K trajectories. | [paper](https://arxiv.org/abs/2604.11135) / [code](https://github.com/Agentic-Intelligence-Lab/AIM) |
| [AHA-WAM](https://arxiv.org/abs/2606.09811) | 2026 | clean: **93.40%**; randomized: **92.20%**; avg: **92.80%** | -- | Real-world four-task average SR: **78.33%**; closed-loop: **24.17 Hz**. | [paper](https://arxiv.org/abs/2606.09811) / [code](https://github.com/serene-sivy/AHA-WAM) |
| [Cosmos Policy](https://arxiv.org/abs/2601.16163) | 2026 | -- | -- | LIBERO average SR: **98.5%**; RoboCasa: **67.1%**; ALOHA average score: **93.6%**. | [paper](https://arxiv.org/abs/2601.16163) / [project](https://research.nvidia.com/labs/cosmos-lab/cosmos-policy/) / [code](https://github.com/NVlabs/cosmos-policy) |
| [EA-WM](https://arxiv.org/abs/2605.06192) | 2026 | -- | -- | WorldArena P3CScore: **76.60**. | [paper](https://arxiv.org/abs/2605.06192) |
| [GE-Act](https://arxiv.org/abs/2508.05635) | 2025 | -- | -- | LIBERO average SR: **96.5%**; CALVIN average subtasks: **4.260**. | [paper](https://arxiv.org/abs/2508.05635) / [code](https://github.com/AgibotTech/Genie-Envisioner) / [project](https://genie-envisioner.github.io/) |
| [GAM (Geometric Action Model)](https://arxiv.org/abs/2606.17046) | 2026 | -- | -- | LIBERO: **97.6%**; LIBERO-Plus: **85.5%**; camera split: **83.1%**; forward latency: **6.9 ms**. | [paper](https://arxiv.org/abs/2606.17046) / [code](https://github.com/cvlab-kaist/Geometric-Action-Model) / [project](https://cvlab-kaist.github.io/Geometric-Action-Model/) |
| [Motus](https://arxiv.org/abs/2512.13030) | 2025 | clean: **88.7%**; randomized: **87.0%** | -- | RoboTwin values are from the Motubrain comparison. | [paper](https://arxiv.org/abs/2512.13030) / [code](https://github.com/thu-ml/Motus) / [comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20) |
| [Motubrain](https://arxiv.org/abs/2604.27792) | 2026 | clean: **95.8%**; randomized: **96.1%** | -- | WorldArena EWMScore: **63.77**. | [paper](https://arxiv.org/abs/2604.27792) / [code](https://github.com/shengshu-ai/Motubrain) / [results](https://github.com/shengshu-ai/Motubrain#evaluation-results) |
| [LingBot-VA](https://arxiv.org/abs/2601.21998) | 2026 | clean: **92.9%**; randomized: **91.5%** | -- | RoboTwin values are from the Motubrain comparison. | [paper](https://arxiv.org/abs/2601.21998) / [code](https://github.com/Robbyant/lingbot-va) / [comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20) |
| [MV-WAM](https://arxiv.org/abs/2606.21088) | 2026 | randomized: **55.7%** without randomized action supervision | -- | Real-world four-task average SR: **77.5%**. | [paper](https://arxiv.org/abs/2606.21088) |
| [VTAM](https://arxiv.org/abs/2603.23481) | 2026 | -- | -- | Contact-rich real-world average SR: **90%** (potato-chip task: **+80%** vs. pi0.5). | [paper](https://arxiv.org/abs/2603.23481) |
| [ImageWAM](https://arxiv.org/abs/2606.19531) | 2026 | clean: **92.65%**; randomized: **93.70%**; avg: **93.18%** | -- | LIBERO: **98.4%**; LIBERO-Plus: **83.1%**; real-world: **84.5%**. | [paper](https://arxiv.org/abs/2606.19531) / [project](https://zhangwenyao1.github.io/ImageWAM/) / [code](https://github.com/yuyangalin/ImageWAM) |
| [X-WAM](https://arxiv.org/abs/2604.26694) | 2026 | clean: **89.8%**; randomized: **90.7%** | Score: **7.69**; SR: **3.83%** | RoboCasa SR: **79.2%**. | [paper](https://arxiv.org/abs/2604.26694) / [code](https://github.com/sharinka0715/X-WAM) / [RoboDojo](https://robodojo-benchmark.com/leaderboard/rollouts/X_WAM?bench=sim) |
| [DiT4DiT](https://arxiv.org/abs/2603.10448) | 2026 | -- | -- | LIBERO: **98.6%**; RoboCasa-GR1: **50.8%**. | [paper](https://arxiv.org/abs/2603.10448) / [code](https://github.com/Mondo-Robotics/DiT4DiT) |
| [mimic-video](https://arxiv.org/abs/2512.15692) | 2025 | -- | -- | LIBERO (scratch) average SR: **93.9%**; real bimanual: **72.0%** packing / **93.0%** handover. | [paper](https://arxiv.org/abs/2512.15692) / [code](https://github.com/mimic-video/mimic-video) |
| [VideoPolicy](https://arxiv.org/abs/2508.00795) | 2025 | -- | -- | RoboCasa average SR: **63%** (50 demos) / **66%** (300 demos); LIBERO-10: **94%**. | [paper](https://arxiv.org/abs/2508.00795) / [project](https://videopolicy.cs.columbia.edu/) / [code](https://github.com/cvlab-columbia/videopolicy) |
| [Video Prediction Policy (VPP)](https://arxiv.org/abs/2412.14803) | 2024 | -- | -- | CALVIN ABC-D average length: **4.29**; MetaWorld-50 average SR: **68.2%**; XHand seen/unseen: **74.9%** / **60.5%**. | [paper](https://arxiv.org/abs/2412.14803) / [code](https://github.com/roboterax/video-prediction-policy) |
| [MemoryWAM](https://arxiv.org/abs/2606.20562) | 2026 | -- | -- | RMBench average SR: **83.0%**; real Shell Game: **18/20**; Look and Press: **15/20**. | [paper](https://arxiv.org/abs/2606.20562) |
| [Fast-WAM](https://arxiv.org/abs/2603.16666) | 2026 | clean: **91.9%**; randomized: **91.8%** | Score: **3.48**; SR: **2.03%** | LIBERO average SR: **97.6%**; inference latency: **190 ms**. | [paper](https://arxiv.org/abs/2603.16666) / [project](https://yuantianyuan01.github.io/FastWAM/) / [RoboDojo](https://robodojo-benchmark.com/leaderboard/rollouts/FastWAM?bench=sim) |
| [DreamZero](https://arxiv.org/abs/2602.15922) | 2026 | -- | -- | AgiBot seen-task progress: **62.2%**; unseen-task progress: **39.5%**; DROID unseen-task SR: **22.5%**. | [paper](https://arxiv.org/abs/2602.15922) / [code](https://github.com/dreamzero0/dreamzero) |
| [RynnVLA-002](https://arxiv.org/abs/2511.17502) | 2025 | -- | -- | LIBERO continuous-action average SR: **97.4%**. | [paper](https://arxiv.org/abs/2511.17502) / [code](https://github.com/alibaba-damo-academy/RynnVLA-002) |
| [DreamVLA](https://arxiv.org/abs/2507.04447) | 2025 | -- | -- | LIBERO average SR: **92.6%**; CALVIN ABC-D average chain length: **4.44**. | [paper](https://arxiv.org/abs/2507.04447) / [code](https://github.com/Zhangwenyao1/DreamVLA) |
| [WorldVLA](https://arxiv.org/abs/2506.21539) | 2025 | -- | -- | LIBERO average SR: **81.8%**; 50-frame world-model FVD: **674.1**. | [paper](https://arxiv.org/abs/2506.21539) / [code](https://github.com/alibaba-damo-academy/WorldVLA) |
| [Unified Video Action Model (UVA)](https://arxiv.org/abs/2503.00200) | 2025 | -- | -- | PushT-M average reward: **88%**; LIBERO-10 SR: **93%**; PushT SR: **98%**. | [paper](https://arxiv.org/abs/2503.00200) / [code](https://github.com/ShuangLI59/unified_video_action) |
| [DyWA](https://arxiv.org/abs/2503.16806) | 2025 | -- | -- | Real-world 6D rearrangement average SR: **68%**; world-model-plus-adaptation ablation: **73.3%**. | [paper](https://arxiv.org/abs/2503.16806) / [project](https://pku-epic.github.io/) |
| [GR-2](https://arxiv.org/abs/2410.06158) | 2024 | -- | -- | 105-task real-world Simple SR: **97.7%**; unseen-environment SR: **87.0%**. | [paper](https://arxiv.org/abs/2410.06158) / [project](https://gr2-manipulation.github.io/) |
| [Dreamitate](https://arxiv.org/abs/2406.16862) | 2024 | -- | -- | Real-world SR: **92.5%** rotation; **85.0%** scooping; **92.5%** sweeping. | [paper](https://arxiv.org/abs/2406.16862) / [project](https://dreamitate.cs.columbia.edu/) |

**SR** means success rate. **FVD** means Frechet Video Distance (lower is better). CALVIN average subtasks or chain length is the average number of consecutively completed subtasks. EWMScore and P3CScore are WorldArena metrics. Relative improvements, when shown in parentheses, are not final benchmark scores.

## Method Records

Each entry gives a short description followed by the core technical idea that distinguishes the method.

### Action Images

Action Images studies visual action representations for robot control. Its paper reports zero-shot success rates over four RLBench tasks and five unseen xArm real-world tasks.

**Innovation:** It represents robot motion as multi-view RGB action images and jointly generates future multi-view video and action trajectories from images and language.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RLBench zero-shot | Average SR: **38.75%** | Pick Cup: 30%; Reach Target: 60%; Close Drawer: 50%; Close Laptop: 15%. |
| Real xArm zero-shot | Average SR: **26.0%** | Place Cup: 40%; Pick Unseen Toy: 20%; Pick Tissue: 15%; Close Drawer: 45%; Close Box: 10%. |

Sources: [paper](https://arxiv.org/abs/2604.06168) / [project](https://actionimages.github.io/) / [code](https://github.com/UMass-Embodied-AGI/ActionImages)

### AIM

AIM is a world-action modeling method evaluated with a 30K-trajectory setup. Its authors report source-specific Easy and Hard RoboTwin 2.0 success rates.

**Innovation:** It introduces spatial value maps as an explicit interface between world prediction and action decoding, using intent-causal attention to route future information through that map.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | Easy: **94.0%**; Hard: **92.1%** | Keep the Easy/Hard protocol label when comparing. |

Sources: [paper](https://arxiv.org/abs/2604.11135) / [code](https://github.com/Agentic-Intelligence-Lab/AIM)

### AHA-WAM

AHA-WAM separates low-frequency world planning from high-frequency closed-loop action execution. It reports RoboTwin 2.0 results without robot-data pretraining and four real-world manipulation tasks.

**Innovation:** It pairs a slow video-DiT planner with a fast action-DiT executor, then uses rolling KV memory, horizon-adaptive offset training, and Observation-Guided Video-Context Routing to reuse long-horizon plans without making control stale.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 (50 tasks) | clean: **93.40%**; randomized: **92.20%**; average: **92.80%** | 100 trials per task in each setting; no robot-data pretraining. |
| Real-world four-task suite | Average SR: **78.33%** | Fold Towel, Organize Desktop, Prepare Soy Milk, and Store Plate. |
| Closed-loop control | **24.17 Hz** | Main model; the paper separately reports a faster distilled variant. |

Sources: [paper](https://arxiv.org/abs/2606.09811) / [code](https://github.com/serene-sivy/AHA-WAM)

### Cosmos Policy

Cosmos Policy is NVIDIA's policy release built around Cosmos world modeling. Its official project page reports aggregate results on LIBERO and RoboCasa as well as real-world ALOHA evaluation.

**Innovation:** It fine-tunes a video model to jointly predict action chunks, future observations/proprioception, and future-state value for model-based planning.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | Average SR: **98.5%** | Average across four task suites. |
| RoboCasa | Average SR: **67.1%** | 24 kitchen-manipulation tasks; the project page reports 50 demonstrations versus 300 for prior SOTA. |
| ALOHA real world | Average score: **93.6%** | Four bimanual manipulation tasks; the paper uses a 0–100 partial-completion score rather than binary SR. |

Sources: [paper](https://arxiv.org/abs/2601.16163) / [project](https://research.nvidia.com/labs/cosmos-lab/cosmos-policy/) / [code](https://github.com/NVlabs/cosmos-policy)

### EA-WM

EA-WM is a world-model method evaluated on WorldArena, where its paper reports the leading P3CScore over six robot-centric metrics.

**Innovation:** It projects actions and kinematic states into camera-view Structured Kinematic-to-Visual Action Fields and fuses them with event-aware bidirectional attention.

| Benchmark | Result | Notes |
| --- | --- | --- |
| WorldArena | P3CScore: **76.60** | Average over six selected normalized metrics, multiplied by 100; 5.52 points above CogVideoX. |

Sources: [paper](https://arxiv.org/abs/2605.06192)

### GE-Act

GE-Act is the action-generation component in Genie Envisioner. The official evaluation instructions publish both CALVIN long-horizon results and LIBERO split-level success rates.

**Innovation:** It turns the pretrained Genie Envisioner video-world backbone into a policy through task-specific video adaptation followed by action post-training with an action expert.

| Benchmark | Result | Notes |
| --- | --- | --- |
| CALVIN | Average subtasks: **4.260** | Official simulation benchmark result. |
| LIBERO | Average SR: **96.5%** | Goal: 95.8%; Object: 97.6%; LIBERO-10: 94.4%; Spatial: 98.2%. |

Sources: [paper](https://arxiv.org/abs/2508.05635) / [code](https://github.com/AgibotTech/Genie-Envisioner) / [official evaluation](https://github.com/AgibotTech/Genie-Envisioner/blob/master/experiments/RUN.md) / [project](https://genie-envisioner.github.io/)

### GAM (Geometric Action Model)

GAM is a separate method from GE-Act above. It adapts a pretrained geometric foundation model into one language-conditioned policy backbone for perception, future prediction, and action decoding.

**Innovation:** It adapts a pretrained geometric foundation model into one shared backbone for perception, future prediction, and language-conditioned action decoding.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | **97.6%** | Reported success rate for the released 1.4B GAM model. |
| LIBERO-Plus | **85.5%** | Reported success rate. |
| Camera split | **83.1%** | Reported success rate. |
| Inference | **6.9 ms** model-forward latency | CUDA graph inference path; not a benchmark score. |

Sources: [paper](https://arxiv.org/abs/2606.17046) / [code](https://github.com/cvlab-kaist/Geometric-Action-Model) / [project](https://cvlab-kaist.github.io/Geometric-Action-Model/)

### Motus

Motus is an embodied robot-control method with publicly reported RoboTwin 2.0 comparison data. The clean and randomized labels are retained rather than collapsed into one number.

**Innovation:** It combines three MoT experts with optical-flow-derived latent actions, enabling one UniDiffuser-style model to switch among world, VLA, inverse-dynamics, video, and joint prediction modes.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | clean: **88.7%**; randomized: **87.0%** | Reported in the Motubrain RoboTwin comparison. |

Sources: [paper](https://arxiv.org/abs/2512.13030) / [code](https://github.com/thu-ml/Motus) / [Motubrain comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20)

### Motubrain

Motubrain combines world-model-oriented representation learning with embodied action prediction. Its project reports RoboTwin 2.0 results as well as a WorldArena EWMScore.

**Innovation:** It uses a UniDiffuser-style formulation to jointly model video dynamics and actions, so one model supports policy learning, world modeling, video generation, inverse dynamics, and joint prediction.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | clean: **95.8%**; randomized: **96.1%** | Source-specific protocol labels. |
| WorldArena | EWMScore: **63.77** | Use the benchmark's named metric rather than treating it as SR. |

Sources: [paper](https://arxiv.org/abs/2604.27792) / [code](https://github.com/shengshu-ai/Motubrain) / [official results](https://github.com/shengshu-ai/Motubrain#evaluation-results)

### LingBot-VA

LingBot-VA is an open vision-action model with publicly reported RoboTwin 2.0 results. Its result is included with its original clean/randomized labels.

**Innovation:** It interleaves video-dynamics prediction and action inference in one autoregressive video-action model, with a dual-stream MoT, asynchronous execution, and KV caching.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | clean: **92.9%**; randomized: **91.5%** | Reported in the Motubrain RoboTwin comparison. |

Sources: [paper](https://arxiv.org/abs/2601.21998) / [code](https://github.com/Robbyant/lingbot-va) / [Motubrain comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20)

### MV-WAM

MV-WAM is a multi-view world-action model evaluated under RoboTwin randomization and across four real-world tasks. The reported RoboTwin result specifically omits randomized action supervision.

**Innovation:** It combines a cross-modality causal mask, manifold-aware optimization, and progress-value regulation to use video and value feedback for action recovery.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | randomized: **55.7%** | Reported without randomized action supervision. |
| Real-world four-task suite | Average SR: **77.5%** | Four-task average reported by the paper. |

Sources: [paper](https://arxiv.org/abs/2606.21088)

### VTAM

VTAM targets contact-rich robot manipulation. Its reported headline result is a real-world average, not a RoboTwin or RoboDojo leaderboard score.

**Innovation:** It adds tactile streams to a pretrained video transformer through lightweight modality-transfer finetuning and tactile regularization that balances cross-modal attention.

| Benchmark | Result | Notes |
| --- | --- | --- |
| Contact-rich real-world tasks | Average SR: **90%** | Potato-chip task: relative **+80%** versus pi0.5. |

Sources: [paper](https://arxiv.org/abs/2603.23481)

### ImageWAM

ImageWAM connects image-world modeling to robot action learning. Its official project page publishes RoboTwin, LIBERO, LIBERO-Plus, real-world, and efficiency results for named model variants.

**Innovation:** It repurposes image-editing foundation models for world-action learning, pairing image-editing training with action flow matching instead of relying on full future-video generation.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | clean: **92.65%**; randomized: **93.70%**; average: **93.18%** | Detailed project-page table; the separate headline strip displays 93.38%, so this index uses the table value. |
| LIBERO | Average SR: **98.4%** | FLUX.2 4B ImageWAM. |
| LIBERO-Plus | Average SR: **83.1%** / **85.2%** | FLUX.2 4B / 9B, respectively. |
| Real-world dual-arm tasks | Average SR: **84.5%** | Project-page comparison with FastWAM at 79.0%. |
| Efficiency | **4.1x** faster; **84.7%** fewer FLOPs | Relative to the project's stated baseline. |

Sources: [paper](https://arxiv.org/abs/2606.19531) / [project](https://zhangwenyao1.github.io/ImageWAM/) / [code](https://github.com/yuyangalin/ImageWAM)

### X-WAM

X-WAM is a world-action-model method with reported RoboTwin 2.0 and RoboCasa evaluations. It also has an official RoboDojo-Sim leaderboard entry.

**Innovation:** It augments a video prior with a lightweight interleaved depth branch for 4D prediction and uses asynchronous noise sampling to decode actions faster than videos.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | clean: **89.8%**; randomized: **90.7%** | Official code release reports average success rates for both settings. |
| RoboCasa | **79.2%** | Reported success rate. |
| RoboDojo-Sim | Score: **7.69**; SR: **3.83%** | Official live-leaderboard snapshot dated 2026-07-27; 42-task, five-dimension protocol. |

Sources: [paper](https://arxiv.org/abs/2604.26694) / [code](https://github.com/sharinka0715/X-WAM) / [RoboDojo rollout record](https://robodojo-benchmark.com/leaderboard/rollouts/X_WAM?bench=sim)

### DiT4DiT

DiT4DiT applies a diffusion-transformer formulation to the joint world/action setting. Its authors report LIBERO and RoboCasa-GR1 results together with efficiency claims.

**Innovation:** It combines a video-generation transformer with flow-matching action prediction in one vision-action model for tabletop and humanoid robot control.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | **98.6%** | Reported success rate. |
| RoboCasa-GR1 | **50.8%** | Reported success rate. |
| Training efficiency | Over **10x** sample efficiency; up to **7x** convergence speed | Relative claims reported by the authors. |

Sources: [paper](https://arxiv.org/abs/2603.10448) / [code](https://github.com/Mondo-Robotics/DiT4DiT)

### mimic-video

mimic-video uses video-based learning for robot control and evaluates on LIBERO, SIMPLER-Bridge, and real bimanual manipulation.

**Innovation:** It extracts imitation supervision from video, so useful behavior signals can be learned with less dependence on dense robot-action annotation.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | Average SR: **93.9%** | Scratch training; Spatial/Object/Goal: 94.2/96.8/90.6. |
| SIMPLER-Bridge | Average SR: **46.9%** / **56.3%** | Default scratch model / per-task video-flow tuning. |
| Real bimanual dexterous manipulation | **72.0%** packing; **93.0%** package handover | Reported with one workspace camera. |
| Data efficiency | **10x** sample efficiency; **2x** convergence speed | Relative claims versus the paper's VLA comparison. |

Sources: [paper](https://arxiv.org/abs/2512.15692) / [code](https://github.com/mimic-video/mimic-video)

### VideoPolicy

VideoPolicy uses video prediction for visual robot control. Its paper publishes aggregate RoboCasa and LIBERO-10 success rates as well as real-world generalization results.

**Innovation:** It makes predicted future video an explicit intermediate policy target, injecting temporal visual foresight into action selection.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboCasa | Average SR: **63%** / **66%** | 50 human demonstrations per task / 300 MimicGen demonstrations per task. |
| LIBERO-10 | Average SR: **94%** | Same protocol used for the paper's UVA comparison. |
| Real-world generalization | Location: **64%**; unseen objects: **74%**; unseen backgrounds: **58%** | Mean across the five reported tasks; 10 rollouts per task and condition. |

Sources: [paper](https://arxiv.org/abs/2508.00795) / [project](https://videopolicy.cs.columbia.edu/) / [code](https://github.com/cvlab-columbia/videopolicy)

### Video Prediction Policy (VPP)

VPP uses video prediction as a policy-learning signal. Its paper reports absolute CALVIN, MetaWorld, and real-robot results alongside relative improvements.

**Innovation:** It turns future-video prediction into a policy-training objective, allowing the controller to benefit from visual trajectory structure beyond immediate action labels.

| Benchmark | Result | Notes |
| --- | --- | --- |
| CALVIN ABC-D | Average task-completion length: **4.29** | Five chained tasks; 10% ABC data setting reaches 3.25. |
| MetaWorld-50 | Average SR: **68.2%** | Easy/Middle/Hard: 81.8/49.3/52.6%. |
| Real Franka Panda | Seen SR: **85.6%**; unseen SR: **73.7%** | Category averages across 30+ tasks. |
| Real XHand dexterous manipulation | Seen SR: **74.9%**; unseen SR: **60.5%** | Category averages across 100+ tasks. |

Sources: [paper](https://arxiv.org/abs/2412.14803) / [code](https://github.com/roboterax/video-prediction-policy)

### MemoryWAM

MemoryWAM adds memory to world-action modeling for longer-horizon interaction. Its paper reports benchmark-wide simulation and real-world scores, in addition to a no-pretraining comparison.

**Innovation:** It adds explicit memory to a WAM so task-relevant visual and action context can persist across long-horizon interaction.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RMBench | Average SR: **83.0%** | Nine memory-dependent tasks; LingBot-VA reaches 78.2%. |
| Observe-and-Pick-Up, no pretraining | **5%** | Appendix comparison; LingBot-VA: 3%. Main RMBench table uses pretraining for this task. |
| Real Shell Game | **18/20** (**90%**) | Number of successes over 20 trials. |
| Real Look and Press | **15/20** (**75%**) | Number of successes over 20 trials. |

Sources: [paper](https://arxiv.org/abs/2606.20562)

### Fast-WAM

Fast-WAM jointly trains on future-video and action targets but skips explicit future-video generation at inference time. It tests whether video co-training can retain representation benefits while meeting real-time control requirements.

**Innovation:** It uses future-video prediction only as a training-time auxiliary target, keeping the representation benefit of imagination without paying for video rollout at test time.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | Average SR: **97.6%** | Reported by the authors. |
| RoboTwin 2.0 | clean: **91.9%**; randomized: **91.8%** | Reported in the Motubrain RoboTwin comparison. |
| RoboDojo-Sim | Score: **3.48**; SR: **2.03%** | Official live-leaderboard snapshot dated 2026-07-27. |
| Inference | **190 ms** latency | Not a benchmark score. |

Sources: [paper](https://arxiv.org/abs/2603.16666) / [project](https://yuantianyuan01.github.io/FastWAM/) / [Motubrain comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20) / [RoboDojo rollout record](https://robodojo-benchmark.com/leaderboard/rollouts/FastWAM?bench=sim)

### DreamZero

DreamZero turns a pretrained video diffusion model into a zero-shot robot policy by jointly predicting actions and future videos. Its paper reports task-progress and success-rate results for AgiBot and DROID-Franka evaluations.

**Innovation:** It converts a pretrained video-diffusion prior into a zero-shot policy by jointly predicting future video and robot actions.

| Benchmark | Result | Notes |
| --- | --- | --- |
| AgiBot seen tasks | Average task progress: **62.2%** | Unseen-environment evaluation; best pretrained VLA baseline: 27.4%. |
| AgiBot unseen tasks | Average task progress: **39.5%** | Ten tasks absent from pretraining. |
| DROID-Franka unseen tasks | Task progress: **49.0%**; SR: **22.5%** | 20 unseen tasks, two rollouts per task. |

Sources: [paper](https://arxiv.org/abs/2602.15922) / [code](https://github.com/dreamzero0/dreamzero)

### RynnVLA-002

RynnVLA-002 is an autoregressive action-world model that unifies image understanding, image generation, and action generation. It extends WorldVLA with continuous actions, wrist-camera input and generation, and robot-state input.

**Innovation:** It unifies image understanding, image generation, continuous actions, wrist views, and robot state in one autoregressive action-world model.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO continuous action | Average SR: **97.4%** | Spatial/Object/Goal/Long: 99.0/99.8/96.4/94.4. |

Sources: [paper](https://arxiv.org/abs/2511.17502) / [code](https://github.com/alibaba-damo-academy/RynnVLA-002)

### DreamVLA

DreamVLA predicts dynamic, spatial, and semantic world knowledge before inverse-dynamics action prediction. The model uses this perception-prediction-action loop for language-conditioned manipulation.

**Innovation:** It makes dynamics, spatial structure, and semantic world knowledge explicit prediction targets before inverse-dynamics action generation.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | Average SR: **92.6%** | Reported by the authors. |
| CALVIN ABC-D | Average chain length: **4.44** | Not directly interchangeable with SR. |

Sources: [paper](https://arxiv.org/abs/2507.04447) / [code](https://github.com/Zhangwenyao1/DreamVLA)

### WorldVLA

WorldVLA represents images, text, and actions in one autoregressive framework. Its design uses joint visual and action prediction so that the world-model and action-model objectives can improve one another.

**Innovation:** It places images, language, and actions in one autoregressive token space, so visual forecasting and action generation improve a shared model.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | Average SR: **81.8%** | 512 × 512 WorldVLA, without pretraining; Spatial/Object/Goal/Long: 87.6/96.2/83.4/60.0. |
| LIBERO world-model video quality | 50-frame FVD: **674.1** | Action World Model result; lower is better. The vanilla-world-model FVD is 718.6. |

Sources: [paper](https://arxiv.org/abs/2506.21539) / [code](https://github.com/alibaba-damo-academy/WorldVLA)

### Unified Video Action Model (UVA)

UVA jointly learns video generation and action prediction with a shared Transformer and separate diffusion heads. At deployment, its decoupled action decoder produces controls without first generating a video rollout.

**Innovation:** It shares a Transformer between video and action learning but decouples the action decoder at deployment, avoiding an expensive video-generation step for control.

| Benchmark | Result | Notes |
| --- | --- | --- |
| PushT | SR: **98%** | 50-rollout single-task evaluation. |
| PushT-M | Average reward: **88%** | 50-rollout multi-task evaluation; not a binary SR. |
| LIBERO-10 | Average SR: **93%** | Average over ten tasks and three random seeds per task. |
| Tool Hang | SR: **88%** | 50-rollout single-task evaluation. |

Sources: [paper](https://arxiv.org/abs/2503.00200) / [code](https://github.com/ShuangLI59/unified_video_action)

### DyWA

DyWA is a point-cloud WAM for non-prehensile manipulation. It jointly predicts actions and future object states while adapting to changes in physical dynamics such as object mass and table friction.

**Innovation:** It uses point clouds to jointly predict future object state and action while explicitly adapting to changed physical dynamics such as mass and friction.

| Benchmark | Result | Notes |
| --- | --- | --- |
| Real-world 6D rearrangement | Average SR: **68%** | CORN baseline: 36%. |
| Simulation ablation | **73.3%** SR | World-model-plus-adaptation setting. |

Sources: [paper](https://arxiv.org/abs/2503.16806) / [project](https://pku-epic.github.io/)

### GR-2

GR-2 is a generative video-language-action model pretrained on web-scale text-video data and then fine-tuned on robot trajectories. It jointly models videos and actions for large multi-task manipulation experiments.

**Innovation:** It transfers web-scale text-video generative pretraining into robot control by jointly modeling language, video, and action trajectories.

| Benchmark | Result | Notes |
| --- | --- | --- |
| 105-task real-world Simple setting | **97.7%** SR | Reported by the authors. |
| Unseen-environment setting | **87.0%** SR | Reported by the authors. |

Sources: [paper](https://arxiv.org/abs/2410.06158) / [project](https://gr2-manipulation.github.io/)

### Dreamitate

Dreamitate fine-tunes a video generator to imagine task executions, tracks the generated tool trajectory in 3D, and executes that trajectory with a robot. The intermediate video plan makes policy behavior inspectable before execution.

**Innovation:** It uses a generated task video as an inspectable plan, converts its tool trajectory into 3D, and then executes that trajectory with the robot.

| Benchmark | Result | Notes |
| --- | --- | --- |
| Real-world object rotation | **92.5%** SR | Reported by the authors. |
| Real-world scooping | **85.0%** SR | Reported by the authors. |
| Real-world tabletop sweeping | **92.5%** SR | Reported by the authors. |

Sources: [paper](https://arxiv.org/abs/2406.16862) / [project](https://dreamitate.cs.columbia.edu/)

## Benchmark Notes

| Benchmark | What this index records | Comparison caution |
| --- | --- | --- |
| [RoboTwin 2.0](https://github.com/RoboTwin-Platform/RoboTwin) | Author-reported success rates with original labels, plus the [official leaderboard](https://robotwin-platform.github.io/leaderboard). | Easy/Hard and clean/randomized use source-specific protocols; do not rank them as if they were one test. |
| [RoboDojo](https://arxiv.org/abs/2607.04434) | A unified sim-and-real benchmark with 42 simulation tasks and 18 real-world tasks across three embodiments. | This index uses the official [live leaderboard](https://robodojo-benchmark.com/leaderboard) snapshot from 2026-07-27: X-WAM (Score 7.69, SR 3.83%) and Fast-WAM (Score 3.48, SR 2.03%) are the only exact matches in this list. |
| LIBERO | Average success rates and per-suite splits when papers publish them. | Task subsets, action parameterization, data processing, and evaluation seeds may differ. |
| LIBERO-Plus | Reported aggregate or split results when explicitly named by the source. | It is not interchangeable with LIBERO. |
| RoboCasa | Reported success rates and the exact variant where available, such as RoboCasa-GR1. | Different RoboCasa variants should remain separately labeled. |
| CALVIN | Chain length or average subtasks, plus explicitly named improvements. | Chain length is not a direct success-rate percentage. |
| WorldArena | Named metrics such as EWMScore and explicit state-of-the-art claims. | Keep the original metric name and evaluation configuration. |

## Inclusion Principles

- Include methods where world prediction, video generation, future-state modeling, or joint world-action learning is directly tied to robot action generation, planning, or closed-loop control.
- Prefer papers with official code, project pages, checkpoints, or evaluation materials.
- Record a result only with its benchmark name, metric, source URL, and any essential protocol qualifier.
- Keep author-reported figures, live leaderboards, and independent reproductions distinct.
- Do not convert incompatible metrics or protocols into a single ranking.

Last checked: 2026-07-27.

## Related Resources

- [Awesome Agent](https://github.com/xinggangw/awesome-agent): structural inspiration for the quick-comparison and per-record format.
- [OpenMOSS Awesome-WAM](https://github.com/OpenMOSS/Awesome-WAM): a broader WAM taxonomy and reading list.
- [Awesome World Action Model](https://github.com/nicolascc1/Awesome-World-Action-Model): another broad world-action-model reading list.
