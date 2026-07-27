# Awesome WAM

A concise, English-language index of **World Action Models (WAMs)** for embodied robot control.

In this list, a WAM is a model in which world prediction, video generation, future-state modeling, or joint world-action learning is a direct part of action prediction, planning, or closed-loop control.

> **Benchmark note.** All numbers and ranks below are reported by the original authors. Evaluation data, action representations, rollout counts, model sizes, and training recipes differ across papers, so the table is a reference index rather than a single comparable leaderboard.

## Quick Comparison

| Method | Year | Key reported benchmark result(s) | Links |
| --- | ---: | --- | --- |
| [Fast-WAM](https://arxiv.org/abs/2603.16666) | 2026 | LIBERO average success rate (SR): **97.6%**; RoboTwin 2.0 SR: **91.8%**; 190 ms inference latency. | [paper](https://arxiv.org/abs/2603.16666) / [project](https://yuantianyuan01.github.io/FastWAM/) |
| [DreamZero](https://arxiv.org/abs/2602.15922) | 2026 | **#1** on RoboArena and MolmoSpaces in the project's February 27, 2026 announcement. | [paper](https://arxiv.org/abs/2602.15922) / [code](https://github.com/dreamzero0/dreamzero) |
| [RynnVLA-002](https://arxiv.org/abs/2511.17502) | 2025 | LIBERO continuous-action SR: **97.4%** average (Spatial/Object/Goal/Long: 99.0/99.8/96.4/94.4). | [paper](https://arxiv.org/abs/2511.17502) / [code](https://github.com/alibaba-damo-academy/RynnVLA-002) |
| [DreamVLA](https://arxiv.org/abs/2507.04447) | 2025 | LIBERO average SR: **92.6%**; CALVIN ABC-D average chain length: **4.44**. | [paper](https://arxiv.org/abs/2507.04447) / [code](https://github.com/Zhangwenyao1/DreamVLA) |
| [WorldVLA](https://arxiv.org/abs/2506.21539) | 2025 | LIBERO grasping SR: **+4%** over its action-only backbone; LIBERO FVD: **10% lower** than its vanilla world model. | [paper](https://arxiv.org/abs/2506.21539) / [code](https://github.com/alibaba-damo-academy/WorldVLA) |
| [Unified Video Action Model (UVA)](https://arxiv.org/abs/2503.00200) | 2025 | **+20%** over the best baseline on PushT-M and **+5%** on LIBERO-10, as reported by the paper. | [paper](https://arxiv.org/abs/2503.00200) / [code](https://github.com/ShuangLI59/unified_video_action) |
| [DyWA](https://arxiv.org/abs/2503.16806) | 2025 | Real-world 6D rearrangement average SR: **68%** (CORN: 36%); simulation world-model-plus-adaptation ablation: **73.3%** SR. | [paper](https://arxiv.org/abs/2503.16806) / [project](https://pku-epic.github.io/) |
| [GR-2](https://arxiv.org/abs/2410.06158) | 2024 | 105-task real-world Simple setting: **97.7%** SR; unseen-environment setting: **87.0%** SR. | [paper](https://arxiv.org/abs/2410.06158) / [project](https://gr2-manipulation.github.io/) |
| [Dreamitate](https://arxiv.org/abs/2406.16862) | 2024 | Real-world SR: **92.5%** object rotation, **85.0%** scooping, and **92.5%** tabletop sweeping. | [paper](https://arxiv.org/abs/2406.16862) / [project](https://dreamitate.cs.columbia.edu/) |

**SR** means success rate. **FVD** means Frechet Video Distance (lower is better). CALVIN average chain length is the average number of consecutively completed subtasks.

## Methods

### Fast-WAM

Fast-WAM jointly trains on future video and action targets, but skips explicit future-video generation at inference time. It tests whether video co-training can provide the representation benefits of a WAM while retaining real-time control.

### DreamZero

DreamZero turns a pretrained video diffusion model into a zero-shot robot policy by jointly predicting actions and future videos. Its release includes checkpoints, training code, and evaluation support for simulation and real-world robot settings.

### RynnVLA-002

RynnVLA-002 is an autoregressive action-world model that unifies image understanding, image generation, and action generation. It extends WorldVLA with continuous actions, wrist-camera input and generation, and robot state input.

### DreamVLA

DreamVLA predicts dynamic, spatial, and semantic world knowledge before inverse-dynamics action prediction. The model uses this perception-prediction-action loop to improve language-conditioned manipulation.

### WorldVLA

WorldVLA represents images, text, and actions in one autoregressive framework. Its design uses joint action and visual prediction so that the world-model and action-model objectives can improve one another.

### Unified Video Action Model (UVA)

UVA jointly learns video generation and action prediction with a shared Transformer and separate diffusion heads. At deployment, its decoupled action decoder can produce controls without first generating a video rollout.

### DyWA

DyWA is a point-cloud WAM for non-prehensile manipulation. It jointly predicts actions and future object states while adapting to changes in physical dynamics such as object mass and table friction.

### GR-2

GR-2 is a generative video-language-action model pretrained on web-scale text-video data and then fine-tuned on robot trajectories. It jointly models videos and actions for large multi-task manipulation experiments.

### Dreamitate

Dreamitate fine-tunes a video generator to imagine task executions, tracks the generated tool trajectory in 3D, and executes that trajectory with a robot. The intermediate video plan makes the policy behavior inspectable before robot execution.

## Related Resources

- [Awesome World Action Model](https://github.com/nicolascc1/Awesome-World-Action-Model): a broader paper taxonomy and reading list.
- [Awesome Agent](https://github.com/xinggangw/awesome-agent): the structural inspiration for this concise index.
