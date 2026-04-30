# Grokene: AI-Guided Ambient-Pressure RTSC Candidate
**arXiv:2601.00931** | DEARDAO DeSci Collaborative Team, Yanhuai Ding | Jan 2026

## 核心方法论
- 用 LLM 引导的材料发现工作流找到 Grokene——一种 graphene 衍生的 2D 超晶格
- 计算流程: DFPT/EPW → Eliashberg → RPA, 全部 first-principles
- 预测 λ 很大, ω_log ≈ 1650 K, mean-field Tc ≈ 325 K
- Full isotropic Eliashberg 给出 Tc ≈ 310 K

## 关键结果
- **BKT 温度仅 ~120 K** (单层), 因为 2D 相涨落
- 提升策略: few-layer stacking, 衬底/栅极工程, 超晶格/掺杂优化
- 整个计算流程锚定在区块链上以保证透明性和可重复性

## 与已有工作的区别
- 非氢化物路线: 基于碳基材料, 常压
- AI 引导材料发现, 非传统高通量筛选
- BKT 问题是核心瓶颈——mean-field Tc 高不等于实验 Tc 高

## 启发的新想法
**[假设]** 对于 2D 超导体, ω_log > 1000 K 可能是常压 RTSC 的必要条件, 但 BKT 温度才是真正的实验门槛. 可以计算: 对于 H₂₄ cage 在 ambient pressure 下是否也存在类似的 mean-field vs BKT gap?

## 与研究的关联
- SC 线 pivot 方向: 非氢化物, 常压, 碳基超导
- ω_log = 1650 K 远高于氢化物 (H₃S ~1100 K), 碳基振动频率天然优势
- BKT 限制是 2D 材料的普遍问题, 需要 3D 结构或层间耦合

## 数值/公式
- ω_log ≈ 1650 K [arXiv:2601.00931]
- mean-field Tc ≈ 325 K, Eliashberg Tc ≈ 310 K [arXiv:2601.00931]
- T_BKT ≈ 120 K (monolayer) [arXiv:2601.00931]
