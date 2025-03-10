#### 智能交通流
针对目前交通流功能单一、交互性不够，上线一套分层架构的交通流框架, 实现在停车场、驾校、
高速路、城区路等场景仿真能力落地
- 基于预测-决策-规划分层设计思想，采用 Grouped-MCTS 方法多车协同决策规划
- 针对场景分布的真实性，采用 diffusion 生成和硬规则约束进行优化
- 完成交通流能力升级，强化停车场、驾校等场景的交互能力，支持 E2E 业务避障效果提升
<video width="560" height="315" controls>
  <source src="static/assets/img/attention.mp4" type="video/mp4">
</video>

#### 数据增强
合成数据能低成本的获取真实路测难以快速采集的数据，通过场景泛化手段增强合成数据和高危 case 的场景
- 由点及面，利用高危 case，基于统一的格式场景描述和 Transformer 架构的轻量级 smart agent 模型泛化产生相似问题场景，验证模型边界能力
- 合成覆盖水马、倒地汽车、轮胎、扫帚等特殊物体数据，改善感知在特殊场景视距 (箱子:8m->28m)
与稳定性不足问题
- 合成覆盖掰出、主辅路、稠密车流、绕行等多种场景数据，改善 PnC 场景不均衡问题

<figure style="text-align: center; margin: 20px auto;">
  <video width="560" height="315" controls>
    <source src="static/assets/img/attention.mp4" type="video/mp4">
    您的浏览器不支持视频标签。
  </video>
  <figcaption>基于注意力机制识别重要障碍物</figcaption>
</figure>