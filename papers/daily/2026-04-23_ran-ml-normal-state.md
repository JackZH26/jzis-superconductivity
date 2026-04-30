# SC-3: Signature of Unconventional SC in High-T Normal State Resistivity
**arXiv:** 2604.16433 | **Authors:** Liu, Lin, Nussinov, Ran (Washington U) | **Year:** 2026

## 核心方法论
用机器学习（线性回归 + 随机森林）训练 Fe 基超导体的常态电阻率数据，发现 150-300K 范围内的输运数据包含是否超导的预测信息。

### 关键结果
1. **分类精度：** 随机森林模型 AUROC = 0.86，accuracy > 80%，能区分超导/非超导样品
2. **Tc 预测较弱：** R² ~ 0.4（RF），说明 Tc 的精确值难以从高温电阻率预测
3. **预测性信息的温度窗口：**
   - 分类信息分布在 150-300K 宽窗口
   - Tc 预测信息集中在 150-200K
   - 200K 以上几乎不含 Tc 预测信息
4. **多通道散射：** 不是单一散射机制（如 T-linear）携带所有信息
   - T¹ 项（strange metal）最重要但不是唯一
   - T² 项（电子-电子）也有显著贡献
   - 去掉 T¹ 项后，T⁰+T²+T³ 组合效果反而更好

### 方法细节
- 175 个数据集（115 超导 + 60 非超导）
- 三阶多项式拟合 ρ(T) = a₀ + a₁T + a₂T² + a₃T³
- 用多项式系数作为特征输入 ML 模型
- 100 次随机训练/测试划分取统计

## 启发的新想法
★ **可验证假设：** 如果 150-300K 的输运数据编码了 SC 信息，那么这暗示**配对相互作用在远高于 Tc 的温度就已经存在**——不只是前驱 Cooper 对效应。对于氢化物超导体（我们的 SC 研究方向），这意味着可以用 300K 的输运性质来筛选候选材料。

**实际应用：** 将此 ML 方法扩展到氢化物：用 DFT 计算的电阻率（Bloch-Boltzmann 输运）作为输入，预测哪些氢化物可能超导。这比目前纯基于 Allen-Dynes/Eliashberg 的方法多了一个独立验证通道。

## 与研究的关联
- 直接相关 SC pivot 方向 c（材料设计）：ML 方法可用于筛选 300K 候选
- T-linear 与 SC 的关联 → Planckian 散射 → 与我们之前读的 Broun/Harrison 论文关联
- 多通道散射思想与 Two-Channel AD 框架一致

## 数值/公式
- 最优温度窗口：T_min = 150K, T_max = 300K
- RF 分类：AUROC = 0.86, accuracy = 81%, sensitivity = 87%, specificity = 68%
- LR 分类：AUROC = 0.82, accuracy = 73%
- RF 回归：R² = 0.42, RMSE = 12.2K
- 数据集：Fe 基超导体（122, 1111, 11 家族）
