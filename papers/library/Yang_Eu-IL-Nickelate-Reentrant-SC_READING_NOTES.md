# 精读笔记：Field Re-entrant Superconductivity in Eu-Doped Infinite-Layer Nickelates

**作者：** Mingwei Yang, Jiayin Tang, Xianfeng Wu, Heng Wang*, ..., **Qikun Xue**, **Zhuoyu Chen***, **Danfeng Li***
**期刊：** **Nature** 主刊 2026-04-23
**DOI：** 10.1038/s41586-026-10547-y
**arXiv：** 2508.14666 (2025-08 提交)
**精读日期：** 2026-04-27

**通讯作者：** Heng Wang (SUSTech), Zhuoyu Chen (SUSTech), Danfeng Li (CityU HK)

---

## 1. 核心发现（一句话）

**首次在高温超导体中发现稳健的"磁场诱导再进入超导"——磁性 Eu²⁺ 重稀土掺杂的无限层镍酸盐，在过掺杂区，磁场（>6T）反而把超导从死回唤回来，能扛到 45 T。**

---

## 2. 材料体系

**Sm₀.₉₅₋ₓCa₀.₀₅EuₓNiO₂（SCEₓ）薄膜，Eu 掺杂浓度 x = 0–0.80**

- **基底：** LSAT (001), 5×5 mm²
- **生长：** PLD（KrF excimer 激光），600°C, 100 mTorr O₂
- **拓扑还原：** 原位 CaH₂ 在 270-310°C 处理，0.5-1.5 小时
- **关键：** Eu²⁺ 离子带 S=7/2 大磁矩；Eu 的 A 位溶解度远超 Sr/Ca

**4 个相图区域：**
| x 范围 | 状态 |
|--------|------|
| x < 0.10 | **绝缘**（与其他掺杂镍酸盐相反）|
| 0.10 ≤ x ≤ 0.45 | **超导**（dome 顶 Tc ≈ 30 K）|
| 0.30 ≤ x ≤ 0.55 | 共存：超导 + **铁磁**（FM）|
| x > 0.45 | 金属，无超导 |

**超导穹顶范围 0.08 < x < 0.5**，比 Nd₁₋ₓEuₓNiO₂ (0.15-0.4) 更宽。

---

## 3. Re-entrant SC 的具体观察

### Sample SCE0.32（24 nm 厚）
- 0–14 T 平面外磁场扫描：
  - 0 → 3 T：Tc 被压制（标准 SC 抑制）
  - 3 → 14 T：**Tc 反而增强**（field-enhanced SC）

### Sample SCE0.34（20 nm 厚）
- T = 2 K，磁场 0 → 9 T：
  - **零电阻在 μ₀H ≥ 6.23 T 重新出现**（第二超导态）
  - 12 T 下双线圈互感测得**Meissner 抗磁信号**确认体超导
  - 形成 "SC → 正常 → SC" 两段相图

### Sample SCE0.32, 高场 35 T（CHMFL Hefei）
- 临界场 3.23 T 后电阻下降
- T = 3 K，**13.04 T 达零电阻**
- **超过 32 T 仍保持零电阻**

### Sample SCE0.36, 极限测量 45 T（CHMFL hybrid 磁体）
- T = 0.3 K，**45 T 仍未压制**重现的零电阻态
- 论文给的下限是 "至少 45 T"

### 角度依赖（关键非常规特征）
- **H⊥sample（垂直膜面）：** Re-entrant 最强
- **H∥sample（平面内）：** Re-entrant **几乎完全消失**
- 这与传统 2D 超导体中 J-P 效应**完全相反**——传统 J-P 在面内场下出现

| 角度 θ（与 c 轴）| Re-entrant 强度 |
|------------------|----------------|
| 0° (H∥c) | 最强 |
| 0–70° | 仍可见 |
| 70–90° (≈H∥ab) | 几乎消失 |

---

## 4. 物理机制

### 候选 1：Jaccarino-Peter 补偿效应（部分成立）
H_total = -H_ex + H_ext，内部交换场 H_ex（来自 Eu²⁺ 局域矩）反对外加场，使总场低于 H_c2
- 解释为什么有 re-entrant
- **不能解释**：J-P 通常需 Eu 矩面内对齐 + H 面内；本工作矩**面外**对齐 + H**面外**

### 候选 2：磁涨落增强配对（near QCP）
- SCE0.34 内同时观测铁磁与超导 → "ferromagnetic SC"
- 隐藏的量子临界点附近的磁涨落能增强配对
- 类似 UTe₂、URhGe、UCoGe 的 spin-triplet 配对

### 论文结论：**两机制（J-P + MF）共同起作用**
- 暗示**自旋三态配对**（spin-triplet）
- 配对方向：Cooper 对自旋沿 c 轴 + 主导层间配对

---

## 5. 关键定量参数（反幻觉，全来自论文原文）

| 参数 | 数值 |
|------|------|
| Tc 最高（onset, x=0.22 附近） | ~30 K |
| 超导穹顶宽度 | 0.08 < x < 0.5 |
| 第二 SC 出现的最低场（SCE0.34）| 6.23 T (T=2K) |
| 完全恢复零电阻场（SCE0.32）| 13.04 T (T=3K) |
| Re-entrant SC 测量上限 | **45 T**（仍不消失）|
| Re-entrant 角度范围 | 0–70°（H 与 c 轴夹角）|
| Eu²⁺ 自旋 | S = 7/2 |
| 磁矩异常增强（SCE0.22）| 400 μB/Eu（由于 Van Vleck）|
| 实测磁矩（SCE0.34, 0.55）| > 10 μB/Eu |
| 理论预期 Eu²⁺ 磁矩 | 7.94 μB/Eu |

---

## 6. 与我们研究的连接

### Paper E（FoP, 已投稿）
- **直接相关**：我们 Paper E 的 P2 预测涉及 SmNiO₂ 的 d 波各向异性
- 本论文 Sm-Ca-Eu-NiO₂ 体系是 SmNiO₂ 的 Eu 掺杂版本
- **新挑战**：如果存在 spin-triplet 配对，需要修正 Paper E 的轨道-能隙原则——膜框架需明确处理 triplet 情形

### Paper A（arXiv:2604.05994，Two-Channel Allen-Dynes）
- Paper A 默认 spin-singlet 配对（自旋涨落介导 d-wave）
- 本论文暗示 nickelate 中**spin-triplet 也可能**（在 ferromagnetic 区）
- 这是 λ_sf 框架的边界——铁磁涨落 vs 反铁磁涨落对配对的相反效应

### 与之前两篇 Nature Physics 论文的连接
1. **Romero et al. (Armitage)** — Planckian scattering + parallel channels（FeTeSe）
2. **Llanos et al. (Falson)** — Field-induced SC in LaSb₂:Ce（J-P 机制）
3. **本论文 Yang et al. (Xue/Chen/Li)** — Field re-entrant SC in Eu-nickelate（J-P + MF 机制）

**三篇都是 2026 年 4 月 Nature 系列发表，主题相关：磁性-超导耦合的新平台**

### Anti-Sycophancy 注意
- **不要把这篇论文当作"Paper E 的实验验证"** ——论文指向 spin-triplet 而 Paper E 默认 singlet
- **正确表述：** 这扩展了 nickelate 配对机制的理论挑战，膜框架应明确说明只适用于 singlet 情形

---

## 7. 论文意义

**这是 Nature 主刊（不是 Nature Physics），影响因子和能见度更高。** 三个原因决定它的重要性：

1. **首次**在高温超导（Tc>30K）发现 robust field re-entrant SC（之前只在 ULow-T heavy-fermion 见过）
2. **首次**观测到 nickelate 中 ferromagnetism 与 superconductivity 共存（同一个样品）
3. **首次**用 Eu 重稀土掺杂建立"超大溶解度"的 nickelate 平台（Eu 比 Sr/Ca 兼容性好）

中国团队（薛其坤-陈卓昱-李丹枫）在 nickelate 方向**继 La₃Ni₂O₇ 后又一篇 Nature**。

---

## 8. 研究方向启示

如果我们想继续 nickelate 方向：

### 短期（理论）
- 把 Eu-doped nickelate 的 spin-triplet 候选纳入膜框架
- 思考 Cooper 对 c 轴自旋 + 层间配对的几何含义

### 中期（实验合作）
- 中国 SUSTech-CityU HK 团队是核心可联系对象
- Eu 掺杂对未来高 Tc 镍酸盐路线意义重大

### 长期（方向）
- Field-induced SC 是 2026 年的 hot topic（Nature/NatPhys 三篇同月）
- 我们之前 Paper A 的 λ_sf 框架未涵盖铁磁涨落贡献，可补充

---

## 9. 推荐后续动作

| 优先级 | 动作 |
|-------|------|
| ⭐⭐⭐ | 写一封简短邮件 introduce 自己 + Paper E 给 Danfeng Li (CityU HK)，建立学术联系 |
| ⭐⭐ | 把 Eu-doped nickelate spin-triplet 配对作为 Paper E 修订时的 caveat 加入 |
| ⭐ | 跟踪薛其坤-陈卓昱-李丹枫接下来的工作（Nature/NatPhys 系列）|

---

**精读总耗时：** 约 30 分钟（PDF 解析 + 全文阅读 + 笔记整理）
**PDF 大小：** 23 MB（26 页全文，含 supplementary）
**存档位置：** `research/papers/library/Yang_Eu-Doped-IL-Nickelate-Reentrant-SC_Nature2026.pdf`
