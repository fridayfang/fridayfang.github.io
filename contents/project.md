#### 可训练的仿真平台
配合数据驱动的需求，重构一套高效支持训练仿真系统，建设类 gym 接口供相关模型组训练
- `效率优化`: 通过核心模块的异步化、核心算法的并行优化、地图缓存等，实现结构化仿真加速比从 0.8 到 3.1
- `接口建设`: 实现类 OpenAI Gym 的接口，搭建 Python 环境，为模型组提供标准化、可扩展性的训练平台
- `业务应用`: 平台上成功实现 PPO（Proximal Policy Optimization) 强化学习算法的训练

#### 智能交通流
针对目前交通流功能单一、交互性不够，上线一套分层架构的交通流框架, 实现在停车场、驾校、
高速路、城区路等场景仿真能力落地
- `分层设计`: 基于预测-决策-规划分层设计思想，采用 Grouped-MCTS 方法多车协同决策规划
- `真实性优化`: 针对场景分布的真实性，采用 diffusion 生成和硬规则约束进行优化
- `业务应用`: 完成交通流能力升级，强化停车场、驾校等场景的交互能力，支持 E2E 业务避障效果提升


#### 数据增强
利用场景泛化和仿真数据，低成本生成真实路测中难以快速采集的数据，从而扩充高风险case场景和合成数据
- `高危case泛化`: 利用高危 case，基于统一的格式场景描述和 Transformer 架构的轻量级 smart agent 模型泛化产生相似问题场景，验证模型边界能力
- `特殊物体与感知优化`:合成覆盖水马、倒地汽车、轮胎、扫帚等特殊物体数据，改善感知在特殊场景视距 (箱子:8m->28m)与稳定性不足问题
- `场景多样性覆盖`: 合成覆盖掰出、主辅路、稠密车流、绕行等多种场景数据，缓解 PnC 场景不均衡问题

<div style="display: flex; justify-content: center; align-items: flex-start; gap: 20px;">
  <figure style="margin: 20px;">
    <video width="560" height="315" controls>
      <source src="static/assets/img/attention.mp4" type="video/mp4">
    </video>
    <figcaption>基于注意力机制识别重要障碍物</figcaption>
  </figure>
  <figure style="margin: 20px;">
    <video width="560" height="315" controls>
      <source src="static/assets/img/fuzzing_demo.mp4" type="video/mp4">
    </video>
    <figcaption>对重要障碍物进行扰动</figcaption>
  </figure>
</div>