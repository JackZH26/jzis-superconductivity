# Unconventional superconductivity from lattice quantum disorder

**arXiv:** 2602.03576 | **作者:** Yu-Cheng Zhu, Jia-Xi Zeng, Xin-Zheng Li (PKU)
**日期:** 2026-02-03

## 核心方法论

使用 **Path-Integral Molecular Dynamics (PIMD)** 在 DFT 水平上处理核量子多体效应，发现了 **Lattice Quantum Disordered (LQD) 相**。

**关键技术：**
- 机器学习原子间势能 (MLIP) 在 DFT-PBE 级别训练
- PIMD 计算质心有效力(centroid potential of mean force)构建自由能面(FES)
- 通过 FES 的曲率变号确定结构相变边界
- 量子(PIMD)边界与经典(MD)边界之间的区域 = LQD 相

## 关键结果

**H₃S：**
- LQD 相在 P-T 图上形成三角形区域
- 左边界（量子边界）精确对齐超导 dome 的左翼
- Tc,LQD^max ≈ **220 K** 对 H₃S, ≈ **160 K** 对 D₃S → 与实验 Tc,SC^max 精确吻合
- 同位素效应被 LQD 相自然解释（D 的量子效应比 H 弱 → Tc 更低）

**La₃Ni₂O₇：**
- Tc,LQD^max ≈ **77 K** 与实验 Tc,SC^max = 80 K 一致
- 左翼的突然下降与 LQD 相边界吻合

**核心论断：** 超导转变（至少在 dome 左翼）起源于低对称→LQD 相的结构转变，超导完全发生在高对称相内。

## 与已有工作的区别

- 以前的理论框架（磁涨落、强关联电子）主要强调电子自由度
- 本文证明：**晶格量子多体效应**是非常规超导的关键成分
- 以前对 H₃S 的"两相解释"被本文推翻——超导完全在 Im3̄m 相内
- LQD 相的晶格动力学超越了传统声子图像

## 与研究的关联

**SC 方向转型启发：** 
- 我们一直用 Eliashberg 理论（传统声子框架），但 LQD 指出声子图像可能不够
- 对于预测新超导体，LQD 相边界可能比 λ、ω_log 更基本
- 需要考虑：我们的 AD/Eliashberg 计算是否忽略了核量子效应？

## 启发的新想法

**假设：** 对预测的室温超导候选材料（如 LaSc₂H₂₄），计算其 LQD 相边界。如果 Tc,LQD^max > 300K，则该材料更可能实现 300K 超导。这比纯粹优化 λ 更可靠。

**可验证：** 用 PIMD 或近似方法计算 H₂₄ cage 结构的量子相变边界。

## 数值/公式

- Tc,LQD^max(H₃S) ≈ 220 K [PIMD, PBE functional, 2602.03576]
- Tc,LQD^max(D₃S) ≈ 160 K [同上]
- Tc,LQD^max(La₃Ni₂O₇) ≈ 77 K [同上]
- 方法: PIMD + MLIP @ DFT-PBE level
