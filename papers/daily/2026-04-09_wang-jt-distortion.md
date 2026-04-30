# Jahn-Teller distortion on strained La₃Ni₂O₇ thin films
- **作者:** Yuxin Wang, Zhan Wang, Fu-Chun Zhang, Kun Jiang
- **来源:** arXiv:2604.02191, cond-mat.supr-con
- **年份:** Apr 2026 (最新！)
- **研究线:** SC
- **精读日期:** 2026-04-09

## 核心贡献（一句话）
系统证明双轴压缩应变主要增强 Jahn-Teller 分裂 ΔJT 而非层间跳跃 t⊥z，从而确立 ΔJT 是 La₃Ni₂O₇ 超导优化的关键微观调控参数。

## 关键方法论
- **DFT + meta-GGA (SCAN)**: 比 GGA 更精确的交换相关泛函，通过固定 a_p、弛豫 c 模拟应变
- **Wannier90 拟合**: 从 DFT 能带提取 4-band tight-binding 参数（ΔJT 和 t⊥z）
- **结构分析**: 区分外层顶氧 Ot 和内层中间氧 Om 的键长响应
  - 压缩 a_p → z_t（Ni-Ot）强烈伸长，z_m（Ni-Om）几乎不变
  - 因此 ΔJT 主要受 a_p 控制，t⊥z 由 z_m 控制
- **ICOHP 分析**: 用 LOBSTER 验证 Ni-Om 键强远大于 Ni-Ot，解释 z_m 不变
- **解耦实验**: 
  - 固定 c，变 a_p: ΔJT 斜率 = **-2.75 eV/Å**（强依赖）
  - 固定 a_p，变 c: ΔJT 斜率 = **+0.38 eV/Å**（弱依赖）
- **Fermi 面 + Hall 系数**: 比较 SLAO（α+β pocket）和 LAO（α+β+γ pocket），γ pocket 的出现/消失由 ΔJT 驱动的 Lifshitz 转变控制
- **块体 vs 薄膜对比**: 静水压下 z_t 和 z_m 同时压缩 → ΔJT 和 t⊥z 同时变化，不可分离

## 主要结果
1. **核心发现**: 应变增强 ΔJT 是超导关键参数（非 t⊥z）
2. ΔJT 对 a_p 斜率 = -2.75 eV/Å，对 c 斜率 = +0.38 eV/Å（7:1 各向异性）
3. SLAO (a_p=3.756Å): 只有 α+β Fermi pocket，RH 更负 → 好超导（Tc~30-48K）
4. LAO (a_p=3.791Å): 多出 γ pocket → Tc 降至 ~3K
5. ΔJT 驱动 Lifshitz 转变：γ pocket 消失对应超导增强
6. 块体静水压不如薄膜应变"干净"——两个参数无法独立调控
7. 超导最优在 dz²⁻ 和 dx²-y²⁻ 近简并的中间区域

## 与我们研究的关联
- **这是 Night 24 的核心参考文献！** 我们 SC latest_state 整个框架就是建立在这篇论文上。
- **ΔJT dome 模型的物理基础**: 我们的 3 点拟合（η_opt=0.378, Tc_max≈55K 薄膜, 87K 块体）直接基于此论文的 DJT 斜率
- **具体可用**: 
  - ΔJT 斜率可以直接预测不同衬底上的超导行为
  - 分子 Mott 绝缘体图像（Wang+ Dec2024）与 JT 调控一致
  - E-field 实验（Yang+ Nature Comm 2026）+ 最优应变组合可预测
- **明天优先事项 #2**: 从此论文 Fig.2 精确提取 SLAO 和 LAO 的 ΔJT 和 t⊥z 数值

## 潜在问题/局限
- meta-GGA/SCAN 仍有系统误差，特别是强关联系统中跳跃参数的定量可靠性
- "无限厚"薄膜近似可能遗漏表面/界面效应
- 没有直接计算 Tc——只提供了电子结构的调控图像
- 实际实验中 Tc onset 和 Tc zero-resistance 差异巨大（onset ~48K, zero-R ~2K）

## 关键数值（全部有来源）
- ΔJT 斜率(a_p): -2.75 eV/Å [Fig.2c]
- ΔJT 斜率(c): +0.38 eV/Å [Fig.2d]
- a_p(SLAO): 3.756 Å
- a_p(LAO): 3.791 Å
- a_p(bulk, ambient): 3.824 Å
- t⊥z: 在应变下近似常数 (~0.6-0.7 eV) [Fig.2b]

## 启发的新想法
- **假设**: 如果 ΔJT dome 存在下降侧，则应变 a_p < 3.73 Å 的衬底（如 YAlO₃, a_p≈3.71Å）上的 LNO 薄膜 Tc 应该低于 SLAO。这是 dome 模型的关键预测。
- **可验证**: 搜索 YAlO₃ 或其他更小 a_p 衬底上 LNO 薄膜的实验数据。如果 Tc 确实下降 → dome 确认；如果 Tc 继续上升 → dome 模型需要修正。
