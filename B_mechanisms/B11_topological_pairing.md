# B11. 拓扑配对（Topological Superconductivity, TSC）

**MECE 编号：** B11
**关联 MECE：** B1（BCS 数学结构 BdG）、B4（spin-triplet — TSC 多由 triplet 实现）、A9（Andreev / Majorana ZBCP）、C5（p 波）、C7（chiral p+ip）、C9（singlet vs triplet）、F4（拓扑分类）、F5（Majorana 零模）、F6（Berry 相 / Chern 数）、D8（重费米子 UTe₂）、D11（半导体纳米线）、D12（TSC 候选 Sr₂RuO₄/β-Bi₂Pd）、D13（Fe(Te,Se) 表面态）、I9（隧穿）、J5（拓扑分类理论）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Kitaev 2001 + Read-Green 2000 + Fu-Kane 2008 + Hasan-Kane 2010 RMP + Sato-Ando 2017 RPP + Microsoft/TU Delft 撤稿事件）

---

## 1. 物理定义与核心思想

**拓扑超导（TSC）：** 配对结构（BdG Hamiltonian）具有非平凡拓扑数的超导态。

[关键特征]
1. **Bulk gap**：体能隙存在
2. **拓扑数** Z 或 Z₂ 不变量（依对称类）
3. **Bulk-boundary correspondence**：边界出现 gapless edge / Majorana 零模
4. **Topology protection**：对小扰动稳定

[与 B1-B10 根本差异]
- B1-B10 关注**配对机制**（什么介导 Cooper 对）
- **B11 关注配对结构的拓扑性质**（不论机制）

> **关键洞察：** TSC 不是新机制，而是**配对态的非平凡拓扑分类**。理论上任何配对机制（B1-B10）都可能产生 TSC，只要配对函数 Δ(k) 在 k-空间有正确的相位结构。

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1937 | Majorana 实粒子方程 | Nuovo Cimento 14, 171 |
| 1991 | Read-Moore Pfaffian state（FQH）| Nucl. Phys. B 360, 362 |
| **2000** | **Read-Green** chiral p+ip TSC + Pfaffian wave function | PRB 61, 10267 |
| **2001** | **Kitaev** 1D Majorana chain | Phys.-Usp. 44, 131 |
| 2003 | Volovik 综述 "The Universe in a Helium Droplet" | Oxford |
| 2005 | 拓扑绝缘体（TI）发现（Kane-Mele）| PRL 95, 226801 |
| 2008 | **Fu-Kane** TI + s-wave SC → 表面 TSC | PRL 100, 096407 |
| **2010** | **Lutchyn-Sau-Das Sarma + Oreg-Refael-von Oppen** 半导体纳米线方案 | PRL 105, 077001; 177002 |
| 2010 | **Hasan-Kane RMP 82, 3045** TI 综述 | DOI |
| 2011 | **Qi-Zhang RMP 83, 1057** TI/TSC 综述 | DOI |
| **2012** | **Mourik et al.** InSb-NbTiN ZBCP（首次 Majorana 候选）| Science 336, 1003 |
| 2014+ | Sr₂RuO₄ chiral p+ip 候选（1998 起累积）| 大量论文 |
| 2017 | Zhang et al. (TU Delft+Eindhoven) "量子化 ZBCP" | Nature 556, 74 |
| **2017** | **Sato-Ando** TSC 综述 | RPP 80, 076501 |
| **2018** | **Zhang et al.** Fe(Te,Se) STM 看到 Majorana ZBCP | Science 360, 182 |
| 2019 | Pustogow Sr₂RuO₄ Knight shift → **修正非 chiral p+ip** | Nature 574, 72 |
| **2021** | **Zhang 2017 撤稿**（数据筛选）；Microsoft 多篇撤回 | Nature 撤稿事件 |
| 2022+ | Microsoft "Majorana 1" 仍在推进，但学界谨慎 | 多篇 |
| 2025 | 拓扑 SC 实验进入"严格判据"时代 | 多篇 |

---

## 3. 数学框架：BdG + 拓扑分类

### 3.1 Bogoliubov-de Gennes（BdG）Hamiltonian

[定义] 标准超导平均场：
$$H_{\text{BdG}}(\mathbf{k}) = \begin{pmatrix} \xi(\mathbf{k}) & \Delta(\mathbf{k}) \\ \Delta^{\dagger}(\mathbf{k}) & -\xi^T(-\mathbf{k}) \end{pmatrix}$$

包含粒子-空穴对称性（C）。结合时间反演（T）和手征（S=CT）给出 10 折分类。

### 3.2 Altland-Zirnbauer（AZ）10 折分类

[来源] Altland-Zirnbauer 1997 PRB 55, 1142

| 类 | T | C | S | 1D 拓扑 | 2D 拓扑 | 3D 拓扑 |
|----|---|---|---|--------|--------|--------|
| A | 0 | 0 | 0 | — | Z | — |
| AIII | 0 | 0 | 1 | Z | — | Z |
| AI | + | 0 | 0 | — | — | — |
| BDI | + | + | 1 | **Z** | — | — |
| D | 0 | + | 0 | **Z₂** | **Z** | — |
| DIII | − | + | 1 | **Z₂** | **Z₂** | **Z** |
| AII | − | 0 | 0 | — | Z₂ | Z₂ |
| CII | − | − | 1 | Z | — | — |
| C | 0 | − | 0 | — | Z | — |
| CI | + | − | 1 | — | — | Z |

[关键 SC 类]
- **D 类（破缺 T）**：chiral p+ip in 2D（Z 拓扑数）
- **DIII（保 T）**：helical p in 2D（Z₂）
- **BDI（保 T + 实参数）**：1D Kitaev chain

### 3.3 Kitaev 1D Chain

[来源] Kitaev 2001 Phys.-Usp. 44, 131 [arXiv:cond-mat/0010440]

**模型：**
$$H = -\sum_j (t\,c^{\dagger}_j c_{j+1} + \Delta\,c^{\dagger}_j c^{\dagger}_{j+1} - \mu\,c^{\dagger}_j c_j) + \text{h.c.}$$

**拓扑相图：**
- |μ| < 2t：拓扑相 → 端点 Majorana zero modes
- |μ| > 2t：trivial

[关键] 链端点的 Majorana operator γ = γ†（自伴随、自共轭）。两个 Majorana 一起组成一个普通费米子。

### 3.4 Read-Green 2D p+ip SC

[来源] Read-Green 2000 PRB 61, 10267 [DOI: 10.1103/PhysRevB.61.10267]

**配对函数：**
$$\Delta(\mathbf{k}) = \Delta_0 (k_x + i k_y)$$

**关键性质：**
- chiral SC，时间反演破缺（TRSB）
- vortex 核心带 Majorana zero mode
- 半奇数热霍尔系数（thermal Hall）
- 对应 5/2 FQH Pfaffian state

### 3.5 Fu-Kane Proximity（关键发现）

[来源] Fu-Kane 2008 PRL 100, 096407 [DOI: 10.1103/PhysRevLett.100.096407]

**关键创新：** 拓扑绝缘体（TI）表面 + 普通 s 波 SC 邻近 → TI 表面态形成 **2D TSC**：
$$H_{\text{surf}} = v(k_x \sigma_y - k_y \sigma_x) - \mu + \Delta(\sigma_y \tau_x)$$

[物理] TI 表面 Dirac 锥 + s 波配对 → spin-momentum 锁定让"effective"配对成为 p+ip 性质 → 拓扑。

[实验候选] Bi₂Se₃ + NbSe₂ 异质结，β-Bi₂Pd, Fe(Te,Se) 表面态。

### 3.6 半导体纳米线方案

[来源]
- Lutchyn-Sau-Das Sarma 2010 PRL 105, 077001 [DOI]
- Oreg-Refael-von Oppen 2010 PRL 105, 177002 [DOI]

**配方：** 半导体纳米线（强自旋轨道）+ s 波 SC + Zeeman 场 + 化学势调控
- B > B_c → 拓扑相
- 端点 Majorana 零模
- ZBCP at V=0 量子化 dI/dV = 2e²/h

---

## 4. 实验候选与争议史

### 4.1 Sr₂RuO₄（教训案例）

[历史]
- 1998-2019：广泛认为 chiral p+ip
- 证据：µSR TRSB、Knight shift "无下降"、HPR 半霍尔
- **2019 Pustogow** Nature 574, 72：Knight shift 修正实验**发现下降** → 推翻 spin-triplet
- **当前共识**：偏向 d 波单态（B3 AFM 涨落驱动）
- µSR TRSB 信号仍存 → 部分 chiral 元素或衰退动力学

[反幻觉] **Sr₂RuO₄ 是 21 世纪凝聚态物理最大判断错误案例**。20 年共识被一个 Knight shift 修正实验推翻。

### 4.2 半导体纳米线 ZBCP 系列（撤稿事件）

| 年份 | 报告 | 后续 |
|------|------|------|
| 2012 | Mourik (TU Delft)：InSb-NbTiN ZBCP | 引发热潮 |
| 2017 | Zhang (TU Delft) Nature："量子化 ZBCP" 2e²/h | **2021 撤稿**（数据筛选）|
| 2018 | Microsoft 多篇报告 | 部分撤回 |
| 2018 | Wang et al. Cu(BiSe)₂ 增强 ZBCP | 多篇质疑 |

[反谄媚关键] 2017-2021 大量"量子化 Majorana ZBCP"声明被撤回。**Pan-Das Sarma 系列论文证明 trivial Andreev 也能给出类似 ZBCP**。

[来源] Pan-Das Sarma 2020+ 多篇，PRB 等

### 4.3 Fe(Te,Se) 表面 Majorana

[来源] Zhang et al. 2018 Science 360, 182 [DOI: 10.1126/science.aan4596]

**实验：** Fe(Te,Se) 单晶 STM 在涡旋核心看到清晰 ZBCP。

**理论**（Wang-Zhang）：
- Fe(Te,Se) bulk 拓扑能带 + s 波 SC 配对
- → 表面 2D TSC（Fu-Kane 类似）
- → 涡旋核心 Majorana zero mode

[现状] 这是当前**最受认可**的 Majorana 候选系统之一。但学界对"trivial vs topological"判据仍谨慎。

### 4.4 UTe₂（重费米子 TSC 候选）

| 性质 | 数据 |
|------|------|
| T_c | 1.6 K |
| Hc2 c-axis | > 30 T（Pauli 违反 ~10×）|
| µSR TRSB | 有信号 |
| Knight shift | 部分下降（争议）|
| 多重 SC 相 | 是 |

[反幻觉] UTe₂ 被推为 spin-triplet TSC 候选，但**Knight shift 数据可能像 Sr₂RuO₄ 一样需要修正**。

### 4.5 β-Bi₂Pd

| 性质 | 数据 |
|------|------|
| T_c | 5 K |
| 表面态 | 拓扑（ARPES 实测）|
| 涡旋 ZBCP | 存在但争议 |

### 4.6 MATBG（Twisted Bilayer Graphene）

| 性质 | 数据 |
|------|------|
| T_c | 1-3 K |
| 配对对称性 | **未确认**（chiral 候选之一）|
| 拓扑 | 候选 |

[反幻觉] MATBG TSC 候选**未确认**，配对机制和对称性都开放。

---

## 5. Majorana 判据演化

### 5.1 早期单一判据（已被推翻）

| 判据 | 问题 |
|------|------|
| ZBCP 存在 | trivial Andreev 也给出 |
| ZBCP 量子化 2e²/h | 多篇声明被撤回 |
| 单一磁场依赖 | 不充分 |

### 5.2 现代多重判据（必要不充分）

[Pan-Das Sarma 2020+ 等] 严格 Majorana 判据要求：

1. **拓扑相变伴随** ZBCP 出现/消失（B 临界值）
2. **量子化 2e²/h**（独立 N-S-N 结构验证）
3. **非局域响应**（multi-terminal cotunneling）
4. **4π 周期 Josephson** 效应
5. **多端关联** Majorana
6. **粒子数寺院测量**（fermion parity）
7. **拓扑保护**（对扰动稳定）

[反幻觉] 任何一个判据都不充分；必须**多个独立判据**联合。

---

## 6. 拓扑分类的扩展

### 6.1 高阶拓扑 SC

[现代] 一阶（边界态）→ 高阶（角态、铰链态）

[实例]
- 二阶 TSC：2D 边界 → 0D 角 Majorana
- 拓扑结晶 SC（mirror, rotation）
- Floquet TSC（驱动诱导）

### 6.2 拓扑节点 SC

[实例]
- Weyl SC（节点）
- Dirac SC（线节点）
- 这些有"节点 fermion arc"边界态

### 6.3 强相关 + 拓扑

[现代前沿]
- TSC + Mott + RVB
- "Fragile topology"（Bouhon-Bzdušek-Slager 等）
- 与 MATBG / Kagome 关联

---

## 7. 限制与边界（反谄媚）

### 7.1 实验确认的稀少

[反谄媚] **至今没有任何 TSC 体系的拓扑性质被严格、多重判据确认**。最强候选（Fe(Te,Se), UTe₂）仍存争议。

### 7.2 撤稿事件的教训

[关键] 2017-2021 大批 Majorana / TSC 实验报告被撤回或质疑。**任何 ZBCP / TRSB 单一信号都不能宣称 TSC**。

### 7.3 Sr₂RuO₄ 案例

20 年共识被 Knight shift 一个修正实验推翻。**长期共识 ≠ 真理**。

### 7.4 trivial vs topological ZBCP

Pan-Das Sarma 等明确证明 trivial Andreev 可产生类 Majorana ZBCP。**简单实验判据不可用**。

### 7.5 拓扑分类的"漂亮"vs物理意义

[反谄媚] 数学上 10 折分类很漂亮，但物理上**实现哪个类需要具体材料**。Lattice + 实际相互作用通常打破纯 AZ 对称性。

### 7.6 与机制（B1-B10）的关系

[关键] B11 不是配对机制（不像 B1-B10）。它分类**配对态的拓扑性质**。所以 B11 必须**依附于某个机制**：
- B1 BCS + spin-triplet → 可能 TSC
- B3 AFM 涨落 + d 波 → 通常不是 TSC（除非加扰动）
- B5 向列 + chiral d±id → 可能 TSC
- 等等

### 7.7 拓扑量子计算的"乐观"

[反谄媚] Microsoft 等推动"拓扑量子计算"，但实验基础仍薄弱。**至今没有 Majorana 公认演示**。商业化承诺远超实验现实。

---

## 8. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B1 BdG** | **数学基础** | BdG Hamiltonian → 拓扑分类 |
| **B4 FM 涨落 / spin-triplet** | **常见 TSC 来源** | p+ip, helical p |
| **B5 向列 / chiral d±id** | TRSB TSC | 候选 |
| **A9 Andreev / Majorana ZBCP** | **核心实验** | 与 TSC 直接关联 |
| **C5 p 波** | 主要配对 | TSC 基础 |
| **C7 chiral p+ip / d±id** | TSC 实例 | TRSB |
| **C9 singlet vs triplet** | 关联 | TSC 多 triplet |
| **F4 拓扑分类** | **同源** | AZ 10 折 |
| **F5 Majorana 零模** | **核心** | TSC 边界态 |
| **D8 重费米子（UTe₂）** | 候选 | spin-triplet TSC |
| **D11 半导体纳米线** | 候选 | Majorana 实验 |
| **D12 拓扑 SC 候选** | **同义** | Sr₂RuO₄, β-Bi₂Pd 等 |
| **D13 Fe(Te,Se) 表面态** | 候选 | Wang-Zhang 提案 |
| I9 隧穿 | 工具 | ZBCP 探测 |
| I6 µSR | 工具 | TRSB 探测 |

---

## 9. 推荐精读论文

### 必读（理论原创）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Read-Green 2000** | DOI: 10.1103/PhysRevB.61.10267 | chiral p+ip + Pfaffian |
| **Kitaev 2001** | arXiv:cond-mat/0010440 | 1D Majorana chain |
| **Fu-Kane 2008** | DOI: 10.1103/PhysRevLett.100.096407 | TI proximity |
| **Lutchyn-Sau-Das Sarma 2010** | DOI: 10.1103/PhysRevLett.105.077001 | 纳米线方案 |
| Oreg-Refael-von Oppen 2010 | DOI: 10.1103/PhysRevLett.105.177002 | 纳米线方案 II |

### 必读综述
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Hasan-Kane 2010 RMP 82, 3045** | DOI: 10.1103/RevModPhys.82.3045 | TI 综述 |
| **Qi-Zhang 2011 RMP 83, 1057** | DOI: 10.1103/RevModPhys.83.1057 | TI/TSC 综述 |
| **Sato-Ando 2017 RPP 80, 076501** | DOI: 10.1088/1361-6633/aa6ac7 | **必读 TSC 综述** |
| Bernevig-Hughes "Topological Insulators" | Princeton 2013 | 教科书 |

### 关键实验
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Mourik et al. 2012 Science 336, 1003 | DOI: 10.1126/science.1222360 | 首个 ZBCP |
| **Pustogow 2019** | DOI: 10.1038/s41586-019-1596-2 | Sr₂RuO₄ 修正 |
| **Zhang et al. 2018 Science 360, 182** | DOI: 10.1126/science.aan4596 | Fe(Te,Se) Majorana |
| Ran et al. 2019 Science 365, 684 | DOI: 10.1126/science.aav8645 | UTe₂ |

### 现代质疑
| 论文 | 来源 | 备注 |
|------|------|------|
| **Pan-Das Sarma 2020+ 多篇** | PRB 等 | trivial vs topological |
| Microsoft / TU Delft 撤稿 | Nature 2021 | 撤稿事件 |

---

## 10. 数据汇总（反幻觉确认）

[定理 - Read-Green 2000] 2D chiral p+ip SC 是 D 类拓扑 SC

[定理 - Kitaev 2001] 1D Majorana chain 在 |μ| < 2t 处于拓扑相

[定理 - Fu-Kane 2008] TI 表面 + s 波 SC → 2D TSC（Fu-Kane proximity）

[定理 - AZ 1997] 10 折拓扑分类按 (T, C, S) 对称性

[观察 - Sr₂RuO₄] 20 年 chiral p+ip 共识被 Pustogow 2019 推翻 → d 波单态

[观察 - 半导体纳米线] 2012 Mourik ZBCP，但 2017-2021 多篇撤回

[观察 - Fe(Te,Se)] Zhang 2018 STM Majorana ZBCP 候选，**未撤回**但仍谨慎

[观察 - UTe₂] Hc2 严重违反 Pauli, µSR TRSB → spin-triplet TSC 候选

[反幻觉] **至今无 TSC 严格、多重判据确认**

[反幻觉] **拓扑量子计算商业化承诺远超实验现实**

---

## 11. 反幻觉自检

- [x] Kitaev 2001 / Read-Green 2000 / Fu-Kane 2008 / Lutchyn-Oreg 2010 / Hasan-Kane / Qi-Zhang / Sato-Ando 经典 DOI 标注
- [x] **Sr₂RuO₄ 修正案例完整说明**
- [x] **Microsoft/TU Delft 撤稿事件（2017-2021）明确**
- [x] **Pan-Das Sarma 质疑系列**包含
- [x] **至今无严格 TSC 确认**坦诚
- [x] AZ 10 折分类完整表
- [x] Fe(Te,Se) Zhang 2018 是当前最强候选明确
- [x] UTe₂ Knight shift 可能修正提示

---

## 12. 反谄媚自检

- [x] **拓扑量子计算商业化承诺过度**坦诚
- [x] **Sr₂RuO₄ 教训反复强调**（20 年共识被推翻）
- [x] **撤稿事件不掩盖**
- [x] B11 **不是配对机制**（依附 B1-B10）明确
- [x] AZ 分类的"数学漂亮 vs 物理实现"区分
- [x] **trivial vs topological ZBCP 区分困难**明确
- [x] MATBG TSC 候选未确认明确
- [x] 单一实验判据不充分明确

---

## 13. 当前状态与后续行动

**状态：** [已综述]，B 部分配对机制（B1-B10）+ 拓扑配对（B11）完整

**关键洞察总结：**

1. **B11 不是新配对机制**，是配对态的拓扑分类
2. **AZ 10 折分类**给出系统拓扑分类框架
3. **Fu-Kane proximity 是关键发现**：s 波 + TI → TSC
4. **半导体纳米线方案**（Lutchyn-Sau, Oreg）成为主流实验方案
5. **Sr₂RuO₄ 教训**：20 年共识 ≠ 真理
6. **撤稿事件（2017-2021）**：单一 ZBCP 信号不充分
7. **当前最强候选**：Fe(Te,Se)（Zhang 2018），UTe₂（争议中）
8. **拓扑量子计算商业化承诺远超实验现实**

**遗留问题：**
1. UTe₂ Knight shift 是否需要类似 Sr₂RuO₄ 修正
2. Fe(Te,Se) Majorana 多重判据严格验证
3. MATBG / Kagome TSC 候选确认
4. 镍酸盐是否含 TSC 元素
5. 高阶 TSC（角 Majorana）实验

**对 Paper A 的关联：**
- Paper A 是 BCS/Eliashberg 框架（弱-中耦合）
- B11 拓扑配对在 Paper A 框架中**未涉及**
- TSC 候选体系（UTe₂, Fe(Te,Se)）超出 Paper A 22 材料 Tier-1 范围

**对 Paper E 的关联：**
- Paper E 是 BCS 数学结构 + 几何重述
- B11 拓扑分类**与 Paper E 几何图像兼容但不同**
  - Paper E 强调 Y_l^m 局部轨道纹理
  - B11 强调 k-空间全局拓扑数
- 两者可结合（拓扑 + 几何），但 Paper E 未做

**B 部分进度（B1-B11 完成 11/14）：**

```
🔵 声子：           B1 + B2 ✅
🟣 自旋：           B3 + B4 ✅
🟠 轨道/晶格：      B5 ✅
🟡 电荷/CDW：       B6 ✅
🟤 激子：           B7 ✅
🟢 等离激元：       B8 ✅
🔮 RVB：            B9 ✅
🟫 Hund's metal：   B10 ✅
🔯 拓扑配对：        B11 ✅ (新)
─────────────────
B 总体: 100% （配对机制 + 拓扑维度）！
缺：B12 多通道叠加 + B13 平坦带 + B14 Mottness（综合性 / 现代主题）
```

**注：** B11 完成后，B 部分的"配对机制和拓扑分类"主线齐备。剩下 B12-B14 是综合性主题：
- **B12 多通道叠加**（Paper A 直接相关）
- **B13 平坦带配对**（Paper E 直接相关）
- **B14 Mottness**（B9 + B14 一起处理）

**后续：** 进入 B12（多通道叠加）— **Paper A 框架核心**

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。Kitaev/Read-Green + Fu-Kane + AZ 分类 + 实验候选完整 + Sr₂RuO₄/纳米线撤稿事件诚实记录 + Paper A/E 边界
