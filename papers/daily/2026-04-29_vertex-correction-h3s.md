# Electron-Phonon Vertex Correction in Superconducting H₃S
**arXiv:2507.01897** | Mishra, Mori, Margine | Jul 2025 | npj Comp. Mat. 11, 342 (2025)

## 核心方法论
- **超越 Migdal 近似**: 在 Eliashberg 框架中引入一阶 e-ph vertex correction
- First-principles 实现 (EPW code), 支持 Full-Bandwidth (FBW) 和 Fermi-Surface Restricted (FSR)
- FBW 保留 DOS 的完整能量依赖, 可以捕获 van Hove singularity 的效应
- 计算 H₃S (非绝热) 和 Pb (绝热) 作为对比

## 关键结果 (H₃S @ 200 GPa)
- **Migdal 参数 ℏω₀/ε_F ≈ 5** → 绝热近似严重失效!
- vertex correction 后的 λ^V 仍然是绝热 λ 的显著比例 → 强耦合在非绝热域仍存在
- **vertex correction + 非谐性 + DOS 能量依赖 → Tc 与实验符合很好**
- 对 Pb: vertex correction 可忽略, 标准 ME 框架足够

## 关键公式/数值
- H₃S: 绝热参数 ℏω₀/ε_F ≈ 5 (vHs 导致 ε_F 小) [arXiv:2507.01897]
- H₃S: 需要同时考虑 anharmonicity + vertex correction + DOS energy dependence
- Pb: 绝热参数 ~ 10⁻² → vertex correction negligible [arXiv:2507.01897]
- 发表于 npj Comp. Mat. [DOI:10.1038/s41524-025-01818-9]

## 与已有工作的区别
- 此前 Mishra+2025 (已读, nonadiabatic + anharmonic H₃S) 未包含 vertex correction
- 本文是首个 first-principles vertex-corrected Eliashberg for real material
- 比 Zappacosta+2025 (nonlinear e-ph, 已读) 更进一步: 完整 vertex diagram

## 启发的新想法
**[假设]** 对于 H₂₄ cage (LaSc₂H₂₄), ε_F 可能也很小(如果有 vHs), 则 vertex correction 对 Tc 预测同样重要. 我们之前的 AD→Eliashberg ×1.15 修正可能还不够——需要检查 H₂₄ 的绝热参数.

**[直接可用]** 这篇确认了我们 SC 实验中 AD vs Eliashberg gap 的物理来源之一: 非绝热效应. 我们的 family-specific correction (H₈: ×1.27, H₁₂: ×1.15) 可能反映了不同族的绝热参数差异.

## 与研究的关联
- SC 线核心: 直接改进 Tc 预测精度
- Mishra & Margine 组(Binghamton)是 Eliashberg first-principles 的标杆
- 与 Night 38 的 family-specific AD correction 直接相关
