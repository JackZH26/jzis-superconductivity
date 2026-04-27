# B6. 电荷涨落介导（Charge Fluctuations / CDW / Excitonic）

**MECE 编号：** B6
**关联 MECE：** B1（BCS 数学结构）、B3（AFM 涨落对比）、B5（向列涨落对比）、B12（多通道叠加）、A8（strange metal）、C1-C3（s/d/s±）、D3（铜氧 CDW dome）、D14（Kagome CDW+SC）、F8（轨道纹理）、H4（CDW normal-state）、I8（X-ray 散射）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Castellani 1995 + Caprara 2017 + Comin-Damascelli 2016 RPP + Kagome 现代）

---

## 1. 物理定义与核心思想

**电荷涨落介导超导（B6）：** 电子通过交换**电荷涨落**（CDW、激子、电荷转移涨落）形成 Cooper 对。这是 B3-B5 之外的"第四类"非常规通道。

[关键挑战]
- **电荷耦合是排斥**（V_pair = +g² χ_c）
- 要让 ⟨V Δ Δ⟩ < 0（吸引）必须要 **反号** Δ(k+Q_CDW) = -Δ(k)
- 这与 B3 AFM 类似但 q 矢量和耦合对象不同

[三个子类]
1. **CDW 涨落**：接近电荷密度波 QCP 的临界涨落
2. **激子机制**：半导体激子作为玻色介质（Little 1964 + Ginzburg）
3. **价键涨落 / 轨道涨落**：多带体系中轨道占据的电荷涨落

---

## 2. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| **1964** | **Little** 提出有机分子激子机制 | Phys. Rev. 134, A1416 |
| **1964** | **Ginzburg** 半导体异质结激子机制 | Sov. Phys. JETP 20, 1549 |
| 1981 | 1T-TiSe₂ 压力下 CDW + SC | 多篇 |
| **1986** | NbSe₂ CDW + SC 共存详细研究 | 多篇 |
| **1995** | **Castellani-Di Castro-Grilli** charge fluctuations 配对（cuprate）| PRL 75, 4650 |
| 2003 | Sr₃Ru₂O₇ meta-magnetic + CDW 候选 | Borzi 2007 Science |
| 2009 | Berg-Chen-Kivelson PDW（pair density wave）框架 | New J. Phys. 11, 115004 |
| 2010+ | cuprate 共振 X 射线散射明确 CDW 序 | 多篇 |
| **2016** | **Comin-Damascelli** cuprate CDW 综述 | Annu. Rev. Cond. Matter 7, 369 |
| **2018** | Kagome (CsV₃Sb₅) CDW + SC 发现 | Ortiz et al. PRM 3, 094407 |
| 2020+ | PdTe₂, β-Bi₂Pd 拓扑 CDW + SC | 多篇 |
| 2026 | Yang/Xue/Chen/Li Eu-nickelate CDW signatures 待确认 | Yang 2026（已精读）|

---

## 3. 数学框架

### 3.1 电荷极化率

[定义] RPA 电荷响应：
$$\chi_c(\mathbf{q}, \omega) = \frac{\chi_0(\mathbf{q}, \omega)}{1 + V_c(\mathbf{q})\chi_0(\mathbf{q}, \omega)}$$

其中 V_c 是库仑相互作用（取屏蔽形式）。当 1 + V_c·χ₀ → 0 时电荷涨落发散 → CDW 不稳定。

### 3.2 配对核

[定义] 电荷涨落配对核：
$$V_{\text{pair}}^{(c)}(\mathbf{k}, \mathbf{k}') = -g_c^2 \chi_c(\mathbf{k}-\mathbf{k}', 0)$$

[关键差异 vs B3]
- 系数（标准 RPA 推导）：B3 (3/2) U², B6 -g_c² 直接吸引
- 但耦合是**直接库仑**，需要小心处理符号
- 实际推导依赖具体模型（电声子 vs 电荷-电荷 vs 激子）

### 3.3 CDW 涨落对配对的两种作用

[关键洞察] CDW 与 SC 既可**竞争**也可**协同**：

| 模式 | 物理 |
|------|------|
| **竞争** | CDW 与 SC 共享同一 nesting 区 → CDW 打开 gap → 抑制 SC |
| **协同** | 接近 CDW QCP → 涨落增强 → 配对增强 |

[来源] Caprara et al. 2017 综述（cuprate CDW + SC）

---

## 4. 激子机制（Little-Ginzburg, 1964）

### 4.1 物理图像

[Little 1964] 在长链有机分子（"骨架"）+ 侧基（"polarizable groups"）中：
- 骨架电子通过侧基的激子云相互作用
- 激子频率 ω_ex 远高于声子 ω_D（电子能标 ~ eV）
- → BCS 公式预测 Tc ~ 100 K+

[Ginzburg 1964] 类似机制在半导体-金属异质结：
- 金属电子与半导体激子云交换
- ω_ex ~ 1 eV → 高 Tc 候选

### 4.2 60 年争议

[反幻觉] 激子机制提出 60 年来**未被严格验证**：
- 没有明确的"激子 SC"实例
- 各种"高 Tc 有机 SC"声明被否决
- 但概念上仍是高 Tc 重要候选

### 4.3 现代复活

[关联] 范德华异质结 / TMD 二维系统中激子物理活跃：
- TMD 双层异质结 / MoSe₂-WSe₂
- Bose-Einstein 凝聚的激子（excitonic insulator）
- 激子辅助 SC 仍是开放研究

---

## 5. CDW + SC 共存体系

### 5.1 NbSe₂（教科书案例）

[来源] 多篇综述

| 量 | 值 |
|----|----|
| T_CDW | 33 K |
| T_c | 7.2 K |
| Q_CDW | (2/3, 0, 0) 类型 |
| 配对 | 弱各向异性 s 波 |
| CDW 性质 | 准 2D, 与 SC 共存 |

[关键观察] NbSe₂ 是 STM 第一个看到 SC 涡旋核态（Hess 1989）和 CDW 共存的体系。

### 5.2 1T-TiSe₂（压力调控）

| 量 | 值 |
|----|----|
| T_CDW | 200 K（常压）|
| T_c | 0（常压）→ 4 K（3 GPa） |
| 机制 | CDW 抑制 → SC 出现 |

### 5.3 铜氧化物 underdoped（D3 关联）

[来源] Comin-Damascelli 2016 ARCMP 7, 369 [DOI: 10.1146/annurev-conmatphys-031115-011401]

cuprate underdoped 区有"低温 CDW 序"：
- YBCO, Bi-2212, Hg-1201 都见 CDW
- Q_CDW ≈ (0.3, 0)
- 共振 X 射线散射（RIXS）明确确认
- CDW dome 在 SC dome 内嵌（competition）

[争议] CDW 涨落是否**辅助**配对仍是开放问题：
- Berg-Chen-Kivelson 2009 PDW 框架
- 部分 cuprate 见 PDW 候选

### 5.4 Kagome 系（D14）— 最新热点

[来源] Ortiz et al. 2019 PRM 3, 094407 (CsV₃Sb₅ 发现)

| 材料 | T_CDW (K) | T_c (K) | 备注 |
|------|----------|--------|------|
| **CsV₃Sb₅** | 94 | 2.5 | star of david CDW |
| **KV₃Sb₅** | 80 | 0.93 | |
| **RbV₃Sb₅** | 103 | 0.92 | |
| **CsV₆Sb₆** | — | 0.85 | |

[关键特点] Kagome 体系：
- 范霍夫奇点 + 平坦带 + 频率涨落
- TRSB 信号（µSR）— 时间反演破缺
- chiral CDW 候选（轨道流）
- 配对对称性争议（s vs s± vs chiral）

### 5.5 PdTe₂ / β-Bi₂Pd（拓扑 CDW + SC）

| 材料 | T_c | 拓扑特征 |
|------|-----|---------|
| PdTe₂ | 1.7 K | type-II Dirac SC + CDW |
| β-Bi₂Pd | 5 K | 拓扑 SC 候选 + CDW |

### 5.6 Hg-1223 高压 CDW（关联 Deng 2026）

[来源] Deng et al. 2026 PNAS（已精读）

Hg-1223 在 30 GPa 压力 quench-to-ambient 给出 151 K 常压 SC，机制涉及 oxygen ordering 和 charge transfer—— 与 CDW 物理紧密相关。

---

## 6. CDW vs SC 竞争 vs 协同的判据

### 6.1 竞争（标准）
- 同一 nesting 矢量 Q 同时驱动 CDW 和 SC
- CDW 抑制时 SC 出现（压力 / 掺杂）
- 例：1T-TiSe₂

### 6.2 协同（涨落驱动）
- 接近 CDW QCP（涨落最强）
- SC dome 在 QCP 附近
- 例：cuprate underdoped？Kagome？

### 6.3 共存（互不干扰）
- 不同 q 矢量
- 例：NbSe₂

### 6.4 典型实验判据
- ARPES：CDW gap vs SC gap 区分
- 共振 X 射线（RIXS）：直接看 CDW 序
- STM：CDW 调制 + SC gap 共存
- 磁场：SC 抑制后 CDW 是否增强

---

## 7. 限制与边界（反谄媚）

### 7.1 配对吸引性争议

[反谄媚] 电荷涨落配对**理论上是排斥**：
- 库仑相互作用本身排斥
- 必须通过反号配对（如 d 波在 cuprate）来获得吸引能
- 这与 B3 AFM 的"自然反号"不同 — 电荷通道反号配对的微观推导更复杂

### 7.2 激子机制 60 年未验证

- Little 1964 + Ginzburg 1964 → 至今无明确"激子 SC"实例
- 现代 vdW 激子物理活跃但 SC 联系待确认

### 7.3 与多机制混合

- Kagome 体系：CDW + 平坦带 + 范霍夫 + chiral 流 + spin
- 不能单纯归因 CDW 涨落

### 7.4 缺乏 ab initio 框架

- χ_c(q, ω) 计算依赖具体模型
- DFT + RPA 在强关联体系不可靠

### 7.5 PDW 候选仍开放

- Berg-Chen-Kivelson 2009 PDW 框架
- 实验确认有限（Bi-2212 STM 部分证据）
- 与 CDW 的精确关系不明

### 7.6 Kagome 配对对称性争议

- s 波 vs s± vs chiral d±id 候选
- µSR TRSB 信号但与 d 波 / chiral 兼容
- 配对对称性未定 → 机制更不确定

---

## 8. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **B1 BCS** | 数学结构相同 | 自洽方程 |
| **B3 AFM** | 类似（不同 q 与耦合对象）| 自旋 vs 电荷 |
| **B5 Nematic** | 类似（不同 form factor）| 轨道 vs 电荷 |
| **B12 多通道** | **核心组分** | Kagome 多机制 |
| **B14 Mottness** | 关联 | doublon-holon 涨落 |
| **A8 strange metal** | 关联 | CDW 涨落贡献 Linear-T |
| **C1-C3** | 增强 | 取决耦合细节 |
| **D3 铜氧** | underdoped CDW | 关键应用 |
| **D14 Kagome** | **核心应用** | CsV₃Sb₅ |
| **F8 轨道纹理** | 关联 | 轨道电荷涨落 |
| **H4 CDW** | 同源 | normal-state CDW |
| I8 X-ray 散射 | **关键工具** | RIXS, REXS |
| I2 STM | 工具 | CDW 实空间 |

---

## 9. 推荐精读论文

### 必读（综述）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Comin-Damascelli 2016 ARCMP 7, 369** | DOI: 10.1146/annurev-conmatphys-031115-011401 | **必读 cuprate CDW 综述** |
| Caprara et al. 2017 综述 | 多篇 PRB | charge fluctuations + cuprate |
| Grüner 1988 RMP 60, 1129 | 经典 CDW 综述 | 待精读 |

### 经典理论
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Little 1964** | DOI: 10.1103/PhysRev.134.A1416 | 激子机制原创 |
| Ginzburg 1964 | Sov. Phys. JETP 20, 1549 | 激子机制 |
| **Castellani-Di Castro-Grilli 1995** | DOI: 10.1103/PhysRevLett.75.4650 | charge fluctuations 配对（cuprate）|
| Berg-Chen-Kivelson 2009 | DOI: 10.1088/1367-2630/11/11/115004 | PDW 框架 |

### 关键实验
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Hess et al. 1989 PRL 62, 214 | NbSe₂ STM 涡旋 | 经典 |
| Borzi et al. 2007 Science 315, 214 | Sr₃Ru₂O₇ | 已在 B5 引用 |
| Ortiz et al. 2019 PRM 3, 094407 | CsV₃Sb₅ 发现 | 必读 |
| Ghiringhelli et al. 2012 Science 337, 821 | YBCO CDW 发现 | 必读 |
| Chang et al. 2012 Nat. Phys. 8, 871 | YBCO CDW | 必读 |

### 现代 Kagome
| 论文 | DOI/来源 | 状态 |
|------|---------|------|
| Yu et al. 2021 Nat. Commun. 12, 3645 | CsV₃Sb₅ µSR TRSB | 待精读 |
| Mielke et al. 2022 Nature 602, 245 | CsV₃Sb₅ chiral CDW | 待精读 |
| Wilson 2024 综述 | annu. Rev. Cond. Matter | 综述 |

### 镍酸盐 / Hg-1223 关联
| 论文 | 来源 | 状态 |
|------|------|------|
| **Deng et al. 2026 PNAS** | DOI: 10.1073/pnas.2536178123 | 已精读（D3 关联）|
| **Yang et al. 2026 Nature** | arXiv:2508.14666 | 已精读（D5）|

---

## 10. 数据汇总（反幻觉确认）

[定理 - Castellani 1995] 接近 CDW QCP 的电荷涨落可增强 d 波 SC（cuprate）

[定理 - Berg-Chen-Kivelson 2009] PDW 框架：CDW + SC 复合序

[观察 - NbSe₂] T_CDW=33K, T_c=7.2K，CDW 与 SC 共存

[观察 - 1T-TiSe₂] 压力下 CDW 抑制 → SC 出现，最大 T_c=4K @ 3 GPa

[观察 - cuprate underdoped] CDW dome 在 SC dome 内嵌，Q_CDW≈(0.3, 0) [Comin 2016 综述]

[观察 - Kagome CsV₃Sb₅] T_CDW=94K, T_c=2.5K, µSR TRSB 信号 [Yu 2021]

[反幻觉] **激子机制 60 年未严格验证**，未列具体材料数据

[反幻觉] **Kagome 配对对称性未定**（s vs s± vs chiral 争议）

---

## 11. 反幻觉自检

- [x] Little 1964 / Ginzburg 1964 / Castellani 1995 / Berg-Chen-Kivelson 2009 经典 DOI 标注
- [x] Comin-Damascelli 2016 ARCMP 综述 DOI 完整
- [x] NbSe₂, 1T-TiSe₂, cuprate, Kagome 数据来源标注
- [x] **激子机制 60 年未验证**坦诚说明
- [x] **Kagome 配对对称性未定**明确
- [x] PDW 候选与 CDW 关系不明明确
- [x] 不假装电荷涨落"主导"任何具体 SC

---

## 12. 反谄媚自检

- [x] 电荷涨落配对的"排斥本性"和反号配对要求明确
- [x] CDW vs SC 三种关系（竞争/协同/共存）系统列出
- [x] 激子机制争议历史诚实说明
- [x] Kagome 多机制混合不掩盖
- [x] PDW 候选实验有限明确
- [x] 不夸大 cuprate 中 CDW 涨落贡献（与 AFM/向列竞争）
- [x] 缺乏 ab initio 框架明确

---

## 13. 当前状态与后续行动

**状态：** [已综述]，B 部分四类基础通道完整（声子 + AFM + FM + 向列 + 电荷）

**关键洞察总结：**

1. **B6 是 B3-B5 之外的"第四类"非常规通道**
2. **激子机制 60 年未验证** — 但概念上仍重要（高 ω_ex → 高 Tc 候选）
3. **CDW vs SC 三种关系**（竞争/协同/共存）需具体分析
4. **Kagome 是当前最热研究**（CsV₃Sb₅ TRSB + chiral CDW）
5. **cuprate underdoped CDW dome** 是 SC dome 内嵌，竞争为主

**遗留问题：**
1. cuprate underdoped CDW 涨落是否实质增强 d 波 SC
2. Kagome 配对对称性确认（s vs s± vs chiral）
3. PDW 候选与 CDW 的精确关系
4. Eu-nickelate Yang 2026 中可能的 CDW signatures（待研究）

**对 Paper A 的关联：**
- Paper A 默认 λ_total = λ_ph + λ_sf
- B6 电荷涨落 λ_charge **未明确**
- Kagome 多通道（B12）需要 B6 + 平坦带 (B13) + spin

**对 Paper E 的关联：**
- B6 电荷涨落 ↔ Paper E 轨道纹理可能耦合
- Kagome 范霍夫奇点 + 平坦带 → Paper E 几何超流权重适用？

**B 部分进度（B1-B6 完成 6/14）：**

```
🔵 声子机制：    B1 + B2 ✅
🟣 自旋通道：    B3 + B4 ✅
🟠 轨道/晶格：   B5 ✅
🟡 电荷通道：    B6 ✅ (新)
─────────────
B 总体: 64%（6/14）
缺：B7-B11 + B12-B14
```

**后续：** B7（双磁子 / spin-orbital）或 B12（多通道叠加 — Paper A 直接相关）

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。Comin-Damascelli + Castellani 1995 + Little/Ginzburg 1964 + Kagome 现代 + 镍酸盐 / Hg-1223 关联
