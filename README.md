# Awesome WAM

A continuously updated, English-language index of **World Action Models (WAMs)** for embodied robot control.

In this index, a WAM is a model where world prediction, video generation, future-state modeling, or joint world-action learning is a direct part of action prediction, planning, or closed-loop control.

[Quick Comparison](#quick-comparison) | [Method Records](#method-records) | [Benchmark Notes](#benchmark-notes) | [Inclusion Principles](#inclusion-principles)

> [!IMPORTANT]
> All figures below are reported by the original authors or official project materials. Datasets, embodiments, action spaces, evaluation protocols, rollout budgets, model sizes, and training recipes differ across papers. This is a source-linked reference index, not a normalized leaderboard.

## Quick Comparison

`N/E` means that the official source did not evaluate the method on that benchmark. `N/R` means that no verified public aggregate or leaderboard score has been added to this index as of the last check. RoboTwin labels are preserved exactly as reported; `Easy/Hard` and `clean/randomized` are not interchangeable protocols.

| Method | Year | RoboTwin 2.0 | RoboDojo | Other key reported result(s) | Links |
| --- | ---: | --- | --- | --- | --- |
| [Action Images](https://arxiv.org/abs/2604.06168) | 2026 | N/E | N/R | RLBench and real xArm: strongest zero-shot SR claim, but no numeric aggregate table. | [paper](https://arxiv.org/abs/2604.06168) / [project](https://actionimages.github.io/) / [code](https://github.com/UMass-Embodied-AGI/ActionImages) |
| [AIM](https://arxiv.org/abs/2604.11135) | 2026 | Easy: **94.0%**; Hard: **92.1%** | N/R | Reported with 30K trajectories. | [paper](https://arxiv.org/abs/2604.11135) / [code](https://github.com/Agentic-Intelligence-Lab/AIM) |
| [Cosmos Policy](https://arxiv.org/abs/2601.16163) | 2026 | N/E | N/R | LIBERO average SR: **98.5%**; RoboCasa average SR: **67.1%**. | [paper](https://arxiv.org/abs/2601.16163) / [project](https://research.nvidia.com/labs/cosmos-lab/cosmos-policy/) / [code](https://github.com/NVlabs/cosmos-policy) |
| [EA-WM](https://arxiv.org/abs/2605.06192) | 2026 | N/E | N/R | WorldArena state-of-the-art claim; no single figure added here. | [paper](https://arxiv.org/abs/2605.06192) |
| [GE-Act](https://arxiv.org/abs/2508.05635) | 2025 | N/E | N/R | LIBERO average SR: **96.5%**; CALVIN average subtasks: **4.260**. | [paper](https://arxiv.org/abs/2508.05635) / [code](https://github.com/AgibotTech/Genie-Envisioner) / [project](https://genie-envisioner.github.io/) |
| [GAM (Geometric Action Model)](https://arxiv.org/abs/2606.17046) | 2026 | N/E | N/R | LIBERO: **97.6%**; LIBERO-Plus: **85.5%**; camera split: **83.1%**; forward latency: **6.9 ms**. | [paper](https://arxiv.org/abs/2606.17046) / [code](https://github.com/cvlab-kaist/Geometric-Action-Model) / [project](https://cvlab-kaist.github.io/Geometric-Action-Model/) |
| [Motus](https://arxiv.org/abs/2512.13030) | 2025 | clean: **88.7%**; randomized: **87.0%** | N/R | Scores appear in the Motubrain RoboTwin comparison. | [paper](https://arxiv.org/abs/2512.13030) / [code](https://github.com/thu-ml/Motus) / [comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20) |
| [Motubrain](https://arxiv.org/abs/2604.27792) | 2026 | clean: **95.8%**; randomized: **96.1%** | N/R | WorldArena EWMScore: **63.77**. | [paper](https://arxiv.org/abs/2604.27792) / [code](https://github.com/shengshu-ai/Motubrain) / [results](https://github.com/shengshu-ai/Motubrain#evaluation-results) |
| [LingBot-VA](https://arxiv.org/abs/2601.21998) | 2026 | clean: **92.9%**; randomized: **91.5%** | N/R | Scores appear in the Motubrain RoboTwin comparison. | [paper](https://arxiv.org/abs/2601.21998) / [code](https://github.com/Robbyant/lingbot-va) / [comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20) |
| [MV-WAM](https://arxiv.org/abs/2606.21088) | 2026 | randomized: **55.7%** without randomized action supervision | N/R | Real-world four-task average SR: **77.5%**. | [paper](https://arxiv.org/abs/2606.21088) |
| [VTAM](https://arxiv.org/abs/2603.23481) | 2026 | N/E | N/R | Contact-rich real-world average SR: **90%** (potato-chip task: relative **+80%** vs. pi0.5). | [paper](https://arxiv.org/abs/2603.23481) |
| [ImageWAM](https://arxiv.org/abs/2606.19531) | 2026 | clean: **92.65%**; randomized: **93.70%**; avg: **93.18%** | N/R | LIBERO average SR: **98.4%**; LIBERO-Plus: **83.1%** (FLUX.2 4B); real-world average SR: **84.5%**. | [paper](https://arxiv.org/abs/2606.19531) / [project](https://zhangwenyao1.github.io/ImageWAM/) / [code](https://github.com/yuyangalin/ImageWAM) |
| [X-WAM](https://arxiv.org/abs/2604.26694) | 2026 | clean: **89.8%**; randomized: **90.7%** | N/R | RoboCasa: **79.2%**. | [paper](https://arxiv.org/abs/2604.26694) / [code](https://github.com/sharinka0715/X-WAM) |
| [DiT4DiT](https://arxiv.org/abs/2603.10448) | 2026 | N/E | N/R | LIBERO: **98.6%**; RoboCasa-GR1: **50.8%**. | [paper](https://arxiv.org/abs/2603.10448) / [code](https://github.com/Mondo-Robotics/DiT4DiT) |
| [mimic-video](https://arxiv.org/abs/2512.15692) | 2025 | N/E | N/R | Reports **10x** sample efficiency and **2x** convergence speed. | [paper](https://arxiv.org/abs/2512.15692) / [code](https://github.com/mimic-video/mimic-video) |
| [VideoPolicy](https://arxiv.org/abs/2508.00795) | 2025 | N/E | N/R | RoboCasa and real-world evaluations are public, but no stable aggregate is quoted here. | [paper](https://arxiv.org/abs/2508.00795) / [project](https://videopolicy.cs.columbia.edu/) / [code](https://github.com/cvlab-columbia/videopolicy) |
| [Video Prediction Policy (VPP)](https://arxiv.org/abs/2412.14803) | 2024 | N/E | N/R | Final aggregate not extracted (relative gains: CALVIN **+18.6%** / **+41.5%**; real dexterous SR **+31.6%**). | [paper](https://arxiv.org/abs/2412.14803) / [code](https://github.com/roboterax/video-prediction-policy) |
| [MemoryWAM](https://arxiv.org/abs/2606.20562) | 2026 | N/R | N/R | Observe-and-Pick-Up without pretraining: **5%**; LingBot-VA comparison: **3%**. | [paper](https://arxiv.org/abs/2606.20562) |
| [Fast-WAM](https://arxiv.org/abs/2603.16666) | 2026 | clean: **91.9%**; randomized: **91.8%** | N/R | LIBERO average SR: **97.6%**; inference latency: **190 ms**. | [paper](https://arxiv.org/abs/2603.16666) / [project](https://yuantianyuan01.github.io/FastWAM/) / [comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20) |
| [DreamZero](https://arxiv.org/abs/2602.15922) | 2026 | N/E | N/R | **#1** on RoboArena and MolmoSpaces in the February 27, 2026 project announcement. | [paper](https://arxiv.org/abs/2602.15922) / [code](https://github.com/dreamzero0/dreamzero) |
| [RynnVLA-002](https://arxiv.org/abs/2511.17502) | 2025 | N/E | N/R | LIBERO continuous-action average SR: **97.4%**. | [paper](https://arxiv.org/abs/2511.17502) / [code](https://github.com/alibaba-damo-academy/RynnVLA-002) |
| [DreamVLA](https://arxiv.org/abs/2507.04447) | 2025 | N/E | N/R | LIBERO average SR: **92.6%**; CALVIN ABC-D average chain length: **4.44**. | [paper](https://arxiv.org/abs/2507.04447) / [code](https://github.com/Zhangwenyao1/DreamVLA) |
| [WorldVLA](https://arxiv.org/abs/2506.21539) | 2025 | N/E | N/R | Final LIBERO aggregates not extracted (relative: grasping **+4%**; FVD **10% lower**). | [paper](https://arxiv.org/abs/2506.21539) / [code](https://github.com/alibaba-damo-academy/WorldVLA) |
| [Unified Video Action Model (UVA)](https://arxiv.org/abs/2503.00200) | 2025 | N/E | N/R | Final scores not extracted (relative: PushT-M **+20%**; LIBERO-10 **+5%**). | [paper](https://arxiv.org/abs/2503.00200) / [code](https://github.com/ShuangLI59/unified_video_action) |
| [DyWA](https://arxiv.org/abs/2503.16806) | 2025 | N/E | N/R | Real-world 6D rearrangement average SR: **68%**; world-model-plus-adaptation ablation: **73.3%**. | [paper](https://arxiv.org/abs/2503.16806) / [project](https://pku-epic.github.io/) |
| [GR-2](https://arxiv.org/abs/2410.06158) | 2024 | N/E | N/R | 105-task real-world Simple SR: **97.7%**; unseen-environment SR: **87.0%**. | [paper](https://arxiv.org/abs/2410.06158) / [project](https://gr2-manipulation.github.io/) |
| [Dreamitate](https://arxiv.org/abs/2406.16862) | 2024 | N/E | N/R | Real-world SR: **92.5%** rotation; **85.0%** scooping; **92.5%** sweeping. | [paper](https://arxiv.org/abs/2406.16862) / [project](https://dreamitate.cs.columbia.edu/) |

**SR** means success rate. **FVD** means Frechet Video Distance (lower is better). CALVIN average subtasks or chain length is the average number of consecutively completed subtasks. EWMScore is the metric reported by WorldArena. Relative improvements are shown in parentheses and are not final benchmark scores.

## Method Records

Each entry gives a short description followed by the core technical idea that distinguishes the method.

### Action Images

Action Images studies visual action representations for robot control. Its project page reports the strongest zero-shot success rates on RLBench and real-world evaluation, but does not publish a numeric aggregate table.

**Innovation:** It represents robot motion as multi-view RGB action images and jointly generates future multi-view video and action trajectories from images and language.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RLBench and real xArm | Strongest zero-shot SR claim | The official project page does not provide one numeric aggregate score. |

Sources: [paper](https://arxiv.org/abs/2604.06168) / [project](https://actionimages.github.io/) / [code](https://github.com/UMass-Embodied-AGI/ActionImages)

### AIM

AIM is a world-action modeling method evaluated with a 30K-trajectory setup. Its authors report source-specific Easy and Hard RoboTwin 2.0 success rates.

**Innovation:** It introduces spatial value maps as an explicit interface between world prediction and action decoding, using intent-causal attention to route future information through that map.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | Easy: **94.0%**; Hard: **92.1%** | Keep the Easy/Hard protocol label when comparing. |

Sources: [paper](https://arxiv.org/abs/2604.11135) / [code](https://github.com/Agentic-Intelligence-Lab/AIM)

### Cosmos Policy

Cosmos Policy is NVIDIA's policy release built around Cosmos world modeling. Its official project page reports aggregate results on LIBERO and RoboCasa as well as real-world ALOHA evaluation.

**Innovation:** It fine-tunes a video model to jointly predict action chunks, future observations/proprioception, and future-state value for model-based planning.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | Average SR: **98.5%** | Average across four task suites. |
| RoboCasa | Average SR: **67.1%** | 24 kitchen-manipulation tasks; the project page reports 50 demonstrations versus 300 for prior SOTA. |
| ALOHA real world | Highest-average-score claim | The project page does not publish one summary number in the text table used here. |

Sources: [paper](https://arxiv.org/abs/2601.16163) / [project](https://research.nvidia.com/labs/cosmos-lab/cosmos-policy/) / [code](https://github.com/NVlabs/cosmos-policy)

### EA-WM

EA-WM is a world-model method evaluated on WorldArena. Its paper presents the WorldArena result as state of the art, but this index does not add an unverified numerical value.

**Innovation:** It projects actions and kinematic states into camera-view Structured Kinematic-to-Visual Action Fields and fuses them with event-aware bidirectional attention.

| Benchmark | Result | Notes |
| --- | --- | --- |
| WorldArena | State-of-the-art claim | A single figure was not verified for this index. |

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

X-WAM is a world-action-model method with reported RoboTwin 2.0 and RoboCasa evaluations.

**Innovation:** It augments a video prior with a lightweight interleaved depth branch for 4D prediction and uses asynchronous noise sampling to decode actions faster than videos.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboTwin 2.0 | clean: **89.8%**; randomized: **90.7%** | Official code release reports average success rates for both settings. |
| RoboCasa | **79.2%** | Reported success rate. |

Sources: [paper](https://arxiv.org/abs/2604.26694) / [code](https://github.com/sharinka0715/X-WAM)

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

mimic-video uses video-based learning for robot control and evaluates on LIBERO plus real bimanual manipulation. Its public headline figures are relative efficiency measures rather than a single aggregate success rate.

**Innovation:** It extracts imitation supervision from video, so useful behavior signals can be learned with less dependence on dense robot-action annotation.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO and real bimanual manipulation | Evaluated | Reports **10x** sample efficiency and **2x** convergence speed. |

Sources: [paper](https://arxiv.org/abs/2512.15692) / [code](https://github.com/mimic-video/mimic-video)

### VideoPolicy

VideoPolicy uses video prediction for visual robot control. Its official project page documents RoboCasa and real-world generalization experiments, but does not expose one stable aggregate score as page text.

**Innovation:** It makes predicted future video an explicit intermediate policy target, injecting temporal visual foresight into action selection.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboCasa and real-world generalization | Evaluated | The project page reports experimental settings and figures but no source-verifiable aggregate to quote here. |

Sources: [paper](https://arxiv.org/abs/2508.00795) / [project](https://videopolicy.cs.columbia.edu/) / [code](https://github.com/cvlab-columbia/videopolicy)

### Video Prediction Policy (VPP)

VPP uses video prediction as a policy-learning signal. Its paper reports separate CALVIN ABC-D improvements in different settings, so the values are intentionally kept separate instead of being treated as the same metric.

**Innovation:** It turns future-video prediction into a policy-training objective, allowing the controller to benefit from visual trajectory structure beyond immediate action labels.

| Benchmark | Result | Notes |
| --- | --- | --- |
| CALVIN ABC-D | Final score not extracted | Relative **+18.6%** in the abstract; **+41.5%** in a different paper setting. |
| Real dexterous manipulation | Final score not extracted | Relative SR improvement: **+31.6%**. |

Sources: [paper](https://arxiv.org/abs/2412.14803) / [code](https://github.com/roboterax/video-prediction-policy)

### MemoryWAM

MemoryWAM adds memory to world-action modeling for longer-horizon interaction. The paper provides a task-specific no-pretraining comparison rather than a broad aggregate leaderboard number.

**Innovation:** It adds explicit memory to a WAM so task-relevant visual and action context can persist across long-horizon interaction.

| Benchmark | Result | Notes |
| --- | --- | --- |
| Observe-and-Pick-Up, no pretraining | **5%** | LingBot-VA comparison in the paper: **3%**. |

Sources: [paper](https://arxiv.org/abs/2606.20562)

### Fast-WAM

Fast-WAM jointly trains on future-video and action targets but skips explicit future-video generation at inference time. It tests whether video co-training can retain representation benefits while meeting real-time control requirements.

**Innovation:** It uses future-video prediction only as a training-time auxiliary target, keeping the representation benefit of imagination without paying for video rollout at test time.

| Benchmark | Result | Notes |
| --- | --- | --- |
| LIBERO | Average SR: **97.6%** | Reported by the authors. |
| RoboTwin 2.0 | clean: **91.9%**; randomized: **91.8%** | Reported in the Motubrain RoboTwin comparison. |
| Inference | **190 ms** latency | Not a benchmark score. |

Sources: [paper](https://arxiv.org/abs/2603.16666) / [project](https://yuantianyuan01.github.io/FastWAM/) / [Motubrain comparison](https://github.com/shengshu-ai/Motubrain#robotwin-20)

### DreamZero

DreamZero turns a pretrained video diffusion model into a zero-shot robot policy by jointly predicting actions and future videos. Its release includes checkpoints, training code, and evaluation support for simulation and real-world robot settings.

**Innovation:** It converts a pretrained video-diffusion prior into a zero-shot policy by jointly predicting future video and robot actions.

| Benchmark | Result | Notes |
| --- | --- | --- |
| RoboArena and MolmoSpaces | **#1** | Project announcement dated February 27, 2026. |

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
| LIBERO grasping | Final SR not extracted | Relative **+4%** versus the action-only backbone. |
| LIBERO video quality | Final FVD not extracted | Relative **10% lower** than the vanilla world model. |

Sources: [paper](https://arxiv.org/abs/2506.21539) / [code](https://github.com/alibaba-damo-academy/WorldVLA)

### Unified Video Action Model (UVA)

UVA jointly learns video generation and action prediction with a shared Transformer and separate diffusion heads. At deployment, its decoupled action decoder produces controls without first generating a video rollout.

**Innovation:** It shares a Transformer between video and action learning but decouples the action decoder at deployment, avoiding an expensive video-generation step for control.

| Benchmark | Result | Notes |
| --- | --- | --- |
| PushT-M | Final score not extracted | Relative **+20%** over the best baseline reported by the paper. |
| LIBERO-10 | Final score not extracted | Relative **+5%** over the best baseline reported by the paper. |

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
| [RoboDojo](https://arxiv.org/abs/2607.04434) | A unified sim-and-real benchmark with 42 simulation tasks and 18 real-world tasks across three embodiments. | Results are continuously updated on the [live leaderboard](https://robodojo-benchmark.com/leaderboard); no unverified snapshot scores are copied here. |
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
