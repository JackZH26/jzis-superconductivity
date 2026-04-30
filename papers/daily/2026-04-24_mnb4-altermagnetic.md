# 精读笔记 — SC induced by altermagnetic spin fluctuations in MnB₄
**arXiv:** 2604.21561 | **作者:** Radevych, Roig, Agterberg, Mazin | **年份:** 2026

## 核心方法论
DFT + DFT+U 磁性分析 + Wannier 化 tight-binding 模型 + BCS gap 方程求解。DFPT 计算排除传统 e-ph 机制后，用 DFT+U 探测隐藏磁性，构建最小二轨道模型分析配对对称性。

## 关键结果
1. **e-ph 机制被排除**：DFPT 计算 Tc < 1 K，实验 14.2 K @ 158 GPa
2. **交替磁(AM)不稳定性最近**：DFT+U 中 AM 态在所有 U > 1 eV 下能量最低，0 GPa 时 U ≈ 1 eV 即可稳定
3. **extended-s 波配对**：各向同性 Heisenberg AM 自旋涨落中，三重态因子使 singlet 配对强度增强 3 倍，p 波被抑制
4. **最小模型**：两个键轨道（Mn-Mn dimer 中心 = 反演中心），FS 为简单"maggot"形状

## 数值/公式
- Tc(实验) = 14.2 K @ 158 GPa [来源: Guo+2024, 原始实验]
- Tc(e-ph, DFPT) < 1 K
- N(εF) = 0.57 eV⁻¹/Mn @ 158 GPa（从 0 GPa 的 0.07 大幅增加）
- AM 配对特征矢量：Δ(k) ∝ cos(k_y/2)cos(k_z/2)

## 与已有工作的区别
这是**首个被提出的交替磁自旋涨落驱动的超导材料**。之前 AFM (q≠0) 和 FM (q=0, M≠0) 自旋涨落超导都有实例，但 AM (q=0, M=0) 超导从未被发现过。

## 启发的新想法
**假设**：如果 MnB₄ 的 AM 超导被实验证实（如通过核磁共振的 Knight shift 测量），则为室温超导开辟了第三种自旋涨落通道。关键可检验预测：extended-s 波应该没有节线，NMR 松弛率应显示 BCS-like 的 coherence peak。

## 与研究的关联
对 SC 线极其重要：
1. 提供了一种全新的非 e-ph 配对机制，可作为 "non-BCS mechanism exploration" 方向的具体案例
2. 方法论上，DFT+U 探测隐藏磁性 → 确定自旋涨落类型 → 构建最小模型的流程可复用
3. 对 300K SC：如果能找到 AM 涨落更强的材料，Tc 可能远超 14 K
