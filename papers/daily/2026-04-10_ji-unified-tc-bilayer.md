# A Unified Understanding of the Experimental Controlling of the Tc of Bilayer Nickelates
- **作者:** Jia-Heng Ji, Yu-Bo Liu, Ming Zhang, Fan Yang
- **来源:** arXiv:2603.14519
- **年份:** 2026
- **研究线:** SC
- **精读日期:** 2026-04-10

## 核心贡献（一句话）
用单轨道 d_{x²-y²} 双层 t-J‖-J⊥ 模型 + DFT 输入参数，统一解释了 Nd/Sm 替换增强 Tc、压力 dome、应变增强、空穴掺杂抑制四种实验现象，证明 J⊥ 是控制 Tc 的关键参数。

## 关键方法论
1. **最小模型**：单 d_{x²-y²} 轨道双层 t-J‖-J⊥ 模型 — d_{z²} 近半填充形成局域矩，通过 Hund 耦合传递 J⊥ 到 d_{x²-y²}
2. **双管齐下求解**：SBMF（slave-boson mean-field）+ DMRG（density-matrix renormalization group）
3. **DFT 参数输入**：不同实验条件下的 TB 参数直接从 DFT 计算获取
4. **DMRG 确定有效 J⊥**：比较双轨道模型和单轨道模型的层间自旋关联，匹配得到有效 J⊥
5. **弱耦合 RPA 对照**：证明强耦合 t-J 模型比弱耦合 RPA 更好地解释实验

## 主要结果
1. **Nd 替换**：J⊥^z 和 J⊥ 随 Nd 含量单调增加 → Tc 单调增加（一致实验）
2. **压力 dome**：J⊥^z 先增后减（18-30 GPa 最大）→ Tc dome（与 Nature 621 一致）
   - 物理原因：低压时 Ni-O-Ni 角趋 180° 增强 t⊥^z → J⊥^z↑；高压时 O-p_z 穿过费米面改变超交换机制 → J⊥^z↓
3. **应变**：压缩应变使 Ni-O-Ni 角 → 180° → t⊥^z↑ → J⊥↑ → Tc↑（一致 SLAO 实验）
4. **空穴掺杂**：增加 δ → 降低 DOS → BCS: Tc ~ exp(-1/(N_Ef·J⊥)) → Tc↓
5. **SBMF 结果**：Tc 由 T_pair 决定（非 T_BEC），因为 δ≈0.5 给出大 T_BEC ≫ T_pair（类似过掺杂铜氧化物）
6. **预测**：电子掺杂（用更高价元素替换 La³⁺）或进一步增强压缩应变可提高 Tc

## 与我们研究的关联
- **★ 直接验证 PSPD 解耦框架**：我们 Night 25 提出的 ΔJT=onset / J⊥=magnitude 双参数解耦与本文完全一致！
  - 本文明确证实：前三种实验（替换、压力、应变）的 Tc 变化**主要源自 J⊥ 的变化**
  - 这验证了我们"J⊥ 控制 Tc magnitude"的核心假设
- **打破 circularity 的新数据**：
  - 本文 Fig.3(a) 给出了 J⊥^z vs P 的 DFT 数据，dome peak at ~30 GPa
  - 这与 Wang+2026 (arXiv:2604.02191) 的 ΔJT 数据互补
- **Hund 耦合传递机制量化**：J⊥ > J⊥^z 在弱 J⊥^z 区间成立 — 因为 d_{z²} 更容易局域化

## 潜在问题/局限
- SBMF + 1D DMRG 只给定性趋势，定量 Tc 值不可靠
- 模型完全忽略 d_{z²}-d_{x²-y²} 面内杂化（声称被强关联抑制，但未严格证明）
- RPA 对比实验中只有压力 dome 一致，其余三种不一致 → 支持强耦合图像但也有争议

## 关键数值（从论文 DFT 提取）
- J_H = 1 eV [adopted]
- U ≈ 5 eV [adopted]
- 空穴掺杂 δ ≈ 0.5（quarter filling of d_{x²-y²}）
- T_BEC ≫ T_pair → Tc = T_pair

## 启发的新想法
1. **★ 直接可验证**：用本文的 J⊥(P) 数据（Fig.3a）+ 我们的 ΔJT(a_p) 数据（from arXiv:2604.02191），建立 Tc(J⊥, ΔJT) 的二维拟合。如果两参数独立性成立，R² 应该显著高于单参数 fit
2. **电子掺杂预测**：本文预测电子掺杂增强 Tc。这是可以搜索的实验验证——查找有无 Ce⁴⁺ 替换 La³⁺ 的实验
3. **J⊥ > J⊥^z 的 Hund 增强效应**：可以定量计算 J⊥/J⊥^z 作为 J_H/U 的函数，为 J⊥ 设定更精确的值
