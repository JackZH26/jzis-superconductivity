# Prediction of several Co-based La3Ni2O7-like superconducting materials
- **作者:** J.-X. Wang, Y.-H. Tian, J.-H. She, R.-Q. He, Z.-Y. Lu
- **来源:** arXiv:2509.09664
- **年份:** 2025
- **研究线:** SC
- **精读日期:** 2026-04-11

## 核心贡献（一句话）
用 DFT+DMFT+RPA 预测了多种 Co 基双层 La3Ni2O7 类似物（LaTh2Co2O7, La3Co2O5Cl2, La3Co2O5Br2）作为高温超导候选材料，电子掺杂后的 Co eg 轨道展现与 Ni 类似的强关联。

## 关键方法论
- **结构设计:** La3Co2O7 在 25 GPa 高压下为 I4/mmm，a=3.703 Å, c=19.174 Å
- **电子掺杂策略:** 用 Th⁴⁺ 替换 La³⁺ 或 Cl⁻ 替换 O²⁻，使 Co 从 +2.5 (d⁶·⁵) → +1.5 (d⁷·⁵)，匹配 La3Ni2O7 的 Ni d⁷·⁵ 构型
- **DFT+DMFT:** 290K 计算，Co eg 轨道的自能 ImΣ(iω_n) 行为与 Ni 极为相似
- **RPA 配对分析:** 在紧束缚模型上做 RPA → 主导配对对称性为 s-wave
- **局部磁矩窗口:** Co 局部磁矩 0.637-0.647 μ_B，精确落在超导最优窗口 0.63-0.68

## 主要结果
1. **[预测]** LaTh2Co2O7: 三片费米面 (α, β, γ)，Uc = 1.01 eV，A1g (s-wave) 配对
2. **[预测]** La3Co2O5Cl2: 两片费米面 (α, β)，Uc = 1.07 eV，s±-wave 配对
3. **[DFT+DMFT]** Co dz² 半填充 → 强关联；dx²-y² 占据 ~0.73 → 仍有 Hund 关联
4. **[关键]** Co 的 non-Fermi-liquid / strange metal 自能行为与 Ni 类似
5. **[扩展]** 三层 RP 类 Co 化合物（类 La4Ni3O10）也值得探索

## 与我们研究的关联
- **扩展 PSPD 框架到 Co 体系：**
  - 如果 ΔJT 和 J⊥ 框架是普适的，它应该也能预测 Co 化合物的超导
  - Co 的 d⁷·⁵ 构型与 Ni 相同 → eg 轨道物理一致
  - 但 Co 的自旋态更复杂（低自旋/高自旋混合）
- **s-wave vs d-wave 争议：** 
  - 本文预测 Co 体系 s-wave，但 Wang+2026 (2604.08319) 用 VMC 得到 Ni 体系 d-wave
  - RPA 和 VMC 方法的差异 + Co vs Ni 的物理差异
- **最优磁矩窗口 0.63-0.68:** 可以用来独立验证我们对 Tc 的预测——如果 PSPD 模型给出的参数对应的磁矩在此窗口内，就增加了一致性

## 潜在问题/局限
- RPA 在强关联极限不可靠，仅能确定配对对称性
- Th 4f 带穿过费米面 → 可能的 Kondo 效应未考虑
- 结构仅在 25 GPa 高压下稳定 → 实验合成困难
- 没有 Tc 定量预测

## 关键数值（如有）
- La3Co2O7 @ 25 GPa: a = 3.703 Å, c = 19.174 Å [DFT]
- Co dz² 占据: ~0.5 (半填充) [DFT+DMFT]
- Co dx²-y² 占据: ~0.73 [DFT+DMFT]
- Co 局部磁矩: 0.637-0.647 μ_B [DFT+DMFT]
- 最优超导磁矩窗口: 0.63-0.68 μ_B [Ref. 33 in paper]

## 启发的新想法
- **[可验证]** 在 PSPD 框架中计算 LaTh2Co2O7 的 ΔJT 和 J⊥。如果 ΔJT > 0.33 eV 且 J⊥ 在合理范围内，预测该材料在高压下超导
- **[新方向]** Co → Fe → Mn 系列的 RP 化合物：如果核心物理是 dz² 层间耦合 + 最优磁矩窗口，可以系统搜索
