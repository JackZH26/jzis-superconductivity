# A10. 准粒子干涉（QPI - Quasi-Particle Interference）

**MECE 编号：** A10
**关联 MECE：** A5（能隙各向异性）、A9（Andreev 隧穿）、C1-C10（配对对称性诊断）、D3-D5（铜氧/铁基/镍酸盐应用）、I2（STM）、F8（轨道纹理）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Hoffman 2002 + Hanaguri 2009 + Fischer 2007 RMP）

---

## 1. 物理定义

**准粒子干涉（QPI）：** 用 STM 测量超导样品在杂质周围的实空间电导图 dI/dV(r, V)，FFT 后得到 q 空间散射模式，反推电子能带与能隙形状。

[关键原理]
1. 杂质散射准粒子从 k 到 k'，q = k' - k 是散射矢量
2. 实空间电荷密度 ρ(r, V) 形成驻波模式（Friedel 振荡）
3. FFT[ρ(r, V)] → ρ̃(q, V) → 重建散射强度 J(q, V)
4. J(q, V) 的峰位置反映**能带**和**能隙**

---

## 2. 理论框架

### 2.1 标准散射理论
[来源] Hoffman et al. 2002 Science 295, 466

对单杂质：
$$\delta\rho(\mathbf{r}, \omega) \sim \int \text{Tr}[\hat{T} G(\mathbf{r}, \omega) G(-\mathbf{r}, \omega)] d^2k$$

其中 G 是单粒子格林函数，T 是杂质 T 矩阵。

### 2.2 SC 状态下：Bogoliubov 准粒子

在 SC 态下，准粒子是电子-空穴叠加（Bogoliubov 准粒子）：
$$\hat{\gamma} = u_k \hat{c}_k - v_k \hat{c}_{-k}^\dagger$$

T 矩阵在 SC 态下含 u_k v_k 因子，反映能隙的相位结构。

### 2.3 关键判据：q 空间峰的演化

| 体系 | q 空间特征 | 物理 |
|------|----------|------|
| **常规 s 波**| 单一散射通道 | 能带 + |Δ| |
| **d 波**| **8 个 BZ 内峰**，能量依赖 | 节点 + 反节点 |
| **s± 多带**| **带间散射** q 与带内 q 区分 | 符号反转 |
| **chiral / triplet** | 不同对称性结构 | 时间反演破缺 |

---

## 3. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| 1993 | Crommie et al. Cu(111) 表面 Friedel 振荡（非 SC）| Nature |
| **2002** | **Hoffman et al.** Bi-2212 第一个 QPI 看到 d 波节点 | Science 295, 466 |
| 2003 | McElroy et al. Bi-2212 QPI 系统化 | Nature 422, 592 |
| **2009** | **Hanaguri et al.** 铁基（Fe(Te,Se)）QPI 看到 s± 符号反转 | Science 328, 474 |
| 2010+ | QPI 在多家族广泛应用 | Fischer 2007 RMP 综述 |
| 2015+ | QPI + Andreev 联合诊断（A9 + A10）| 多篇 |

---

## 4. d 波 SC 的 QPI（Hoffman 2002 突破）

### 4.1 Bi-2212 的 8 峰图样

[来源] Hoffman et al. 2002 Science 295, 466 [DOI: 10.1126/science.1066974]

[关键观察] Bi-2212 在 4 K 下 STM 看到 dI/dV(r, V) 在不同偏压下有不同图样，FFT 得到 8 个清晰峰位 q₁-q₇。

[物理解释] **d 波等能线**为弧形（"banana"），杂质散射在弧端点之间（"hot spots"）给出特定 q 值：
- q₁: 节点-反节点散射
- q₇: 节点-节点
- 等等

[判据] 如果是 s 波，能隙各向同性，QPI 图样不会有这种 V 依赖结构。Hoffman 数据**否决 s 波**，**支持 d 波**。

### 4.2 dispersing q vs non-dispersing q

| 类型 | 物理 |
|------|------|
| Dispersing q(V) | 能带散射（能量依赖）|
| Non-dispersing q | CDW、配对密度波（PDW）固定 q |

[来源] Davis-Hudson 2013 PNAS 在 Bi-2212 underdoped 看到 non-dispersing q（PDW 候选）

---

## 5. s± 配对的 QPI（Hanaguri 2009 突破）

[来源] Hanaguri et al. 2009 Science 328, 474 [DOI: 10.1126/science.1187399]

### 5.1 关键判据：磁场依赖
铁基 SC 中带间散射强度依赖于磁场：
- 非磁性杂质 + 磁场 → 增强带间散射（s± 符号反转标志）
- 磁性杂质 + 磁场 → 抑制带间散射

[判据] Hanaguri 在 Fe(Te,Se) 中观察到非磁性杂质 + 磁场增强 → **支持 s± 配对**。

### 5.2 局限
- 必须有合适的杂质密度
- 磁场需要足够大但不破坏 SC
- 对样品质量要求高

---

## 6. QPI 与其他诊断的对比

| 诊断方法 | 测量量 | 优势 |
|---------|--------|------|
| **QPI** (A10) | q 空间散射结构 | 能隙符号 + 节点 + 实空间 |
| **ARPES** (I1) | k 空间能带 | 直接看费米面 + 能隙 |
| **Andreev 隧穿** (A9) | 能隙 Δ + ABS | ZBCP 节点判据 |
| **µSR** (I6) | λ_L(T) | 节点低 T 行为 |
| **NMR** (I4) | 1/T₁ Knight shift | 节点 + 三重态判据 |

[关键应用] 多种独立技术联合诊断配对对称性 — 单一技术不足以确认。

---

## 7. 各家族 QPI 研究现状

### 7.1 铜氧化物（D3）
- Bi-2212：QPI 最成熟应用，d 波证据
- YBCO：表面问题，QPI 较少
- LSCO：CDW + QPI 联合
- Hg-1223：QPI 数据少（高质量样品困难）
- **NbSe₂**（虽非铜氧）：第一个 STM 涡旋成像，CDW + SC 共存

### 7.2 铁基（D4）
- Fe(Te,Se)：Hanaguri 2009 突破
- BaFe₂(As,P)₂：节点结构 QPI
- **Fe-based** 在 D4 部分有大量 QPI 文献

### 7.3 镍酸盐（D5）
- **当前 QPI 数据极少**
- La₃Ni₂O₇ STM 困难（薄膜样品 + 表面问题）
- 是 D5 研究的明确空白

### 7.4 重费米子（D8）
- UTe₂、CeCoIn₅：QPI 在低 T 下进行
- 节点结构争议，QPI 是关键工具

### 7.5 拓扑 SC 候选（D12）
- Sr₂RuO₄：QPI 研究 chiral 候选
- β-Bi₂Pd：QPI + Andreev 联合

### 7.6 MATBG（D11）
- 平坦带 + 大单胞使 QPI 解读困难
- 当前研究活跃

---

## 8. 测量方法（实验细节）

### 8.1 STM 设置
- 极低 T（10 mK – 4 K）
- 大磁场（典型 0-12 T）
- 振动隔离 + 屏蔽
- 商业 STM（PPMS、Unisoku）+ 自建

### 8.2 FFT 数据分析
1. 测 dI/dV(r, V) 在多个偏压 V
2. FFT 得到 |F[dI/dV]|(q, V)
3. 识别 dispersing peaks
4. 与理论计算（T 矩阵）对比

### 8.3 各家族常用偏压范围
| 家族 | 典型 Δ | V 扫描范围 |
|------|--------|-----------|
| Bi-2212 | 35 meV | -50 to 50 mV |
| Fe(Te,Se) | 2.5/4 meV | -10 to 10 mV |
| 重费米子 | µeV | µV 级精度 |

### 8.4 联合 ARPES 验证
- ARPES 给出能带 → 提取 k_F → 计算预期 q 散射矢量
- QPI 实测 q vs ARPES 预期 q 的吻合度是判据

---

## 9. 已知例外 / 复杂情形

### 9.1 表面态影响
- 拓扑 SC 候选材料表面态可能贡献 QPI
- 必须区分体相 vs 表面

### 9.2 PDW（配对密度波）
- Non-dispersing q 信号
- 在某些 underdoped cuprate 中观察
- 与 d 波竞争

### 9.3 CDW 与 SC 共存
- CDW 给出固定 q 峰
- 与 SC 散射混合
- 必须分离

### 9.4 多带嵌套
- 铁基多 Fermi 表面给出复杂 QPI
- 拟合困难

### 9.5 杂质类型敏感性
- 磁 vs 非磁杂质影响不同
- 杂质密度过高 → 散射模糊化

### 9.6 各向异性能隙的 QPI 解读
- d 波 vs s± 多带 vs 其他
- 单一 QPI 测量不足以唯一确定

### 9.7 时间反演破缺态（chiral d±id, p±ip）
- 复能隙的 QPI 形态特殊
- 需要联合 µSR / Kerr 旋转

---

## 10. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| **A5 能隙** | **核心工具** | QPI 给出能隙各向异性 |
| **A9 Andreev** | 互补 | 能谱（Andreev）+ 实空间（QPI）|
| **C1-C10 配对对称性** | **诊断关键** | d 波 / s± / chiral / triplet 判据 |
| **C8 PDW** | 关键工具 | non-dispersing q 信号 |
| **F8 轨道纹理** | 关联 | Paper E 的 Y_l^m 纹理可被 QPI 看到 |
| H4 CDW | 干扰 | CDW q 与 SC q 混合 |
| **D3, D4** | 主要应用 | 铜氧 + 铁基 |
| **D12** | 关键判据 | 拓扑 SC 候选验证 |
| I2 STM | 工具 | 必需技术 |

---

## 11. 推荐精读论文

### 必读（核心数据）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| **Hoffman et al. 2002** | DOI: 10.1126/science.1066974 | Bi-2212 第一个 QPI（d 波证据）|
| **Hanaguri et al. 2009** | DOI: 10.1126/science.1187399 | Fe(Te,Se) s± 验证 |
| McElroy et al. 2003 | DOI: 10.1038/nature01496 | Bi-2212 系统 QPI |

### 综述
| 论文 | 来源 | 状态 |
|------|------|------|
| **Fischer et al. 2007 RMP 79, 353** | DOI: 10.1103/RevModPhys.79.353 | **STM in SC 必读综述** |
| Davis-Hudson 2013 PNAS 110, 17623 | PDW QPI | 待精读 |
| Hoffman 2011 Reports on Progress in Physics 74, 124513 | QPI 综述 | 待精读 |

### 现代关键
| 论文 | 来源 | 状态 |
|------|------|------|
| Allan et al. 2013 Science 340, 720 | Cuprate QPI 高分辨 | 待精读 |
| Sprau et al. 2017 Science 357, 75 | FeSe QPI 节点结构 | 待精读 |
| Madhavan QPI on Bi-2212 多篇 | Cornell group | 待精读 |

### 拓扑 SC
| 论文 | 来源 | 状态 |
|------|------|------|
| Madhavan QPI on Sr₂RuO₄ 综述 | 待精读 |
| Wang QPI on β-Bi₂Pd | 待精读 |

---

## 12. 数据汇总（反幻觉确认）

[定理 - 标准散射理论] J(q, V) ∝ Im Σ_k T(k, k+q) G(k, V) G(k+q, V)

[观察 - Hoffman 2002] Bi-2212 8 个 q 峰随 V 演化 → 支持 d 波

[观察 - Hanaguri 2009] Fe(Te,Se) 非磁杂质 + 磁场增强带间 q 散射 → 支持 s±

[观察 - Davis-Hudson 2013] Bi-2212 underdoped non-dispersing q 信号 → PDW 候选

[反幻觉] QPI 测量解读对**杂质类型 + 能带模型 + 拟合范围**敏感。每个数据点应附实验细节。

---

## 13. 反幻觉自检

- [x] Hoffman 2002 + McElroy 2003 + Hanaguri 2009 三个里程碑 DOI 完整
- [x] Fischer 2007 RMP 综述 DOI（DOI: 10.1103/RevModPhys.79.353）
- [x] 镍酸盐 QPI 数据空白明确
- [x] 不混淆 Bi-2212 d 波证据与"d 波普适"
- [x] PDW non-dispersing q 与 SC dispersing q 的区分
- [x] 不假装 QPI 唯一决定配对对称性

## 14. 反谄媚自检

- [x] 多家族 QPI 现状坦诚说明（包括镍酸盐空白）
- [x] QPI 解读复杂性（杂质 / 能带 / PDW / CDW）明确列出
- [x] 拓扑 SC QPI 仍有争议
- [x] 不夸大 Hanaguri s± 证据为"完全确认"——多体系仍开放
- [x] FeSe 节点结构争议明确

---

## 15. 当前状态与后续行动

**状态：** [已综述] — **A 部分最后一个综述**

**遗留问题：**
1. 镍酸盐 QPI 是 D5 明确空白 — 高质量样品 + STM 是关键
2. UTe₂ QPI 与 spin-triplet 节点结构（→ D8, G7）
3. PDW vs CDW 在不同 cuprate 体系的相图
4. MATBG QPI 解读（与平坦带相结合）

**与 Paper E 的关联：**
- Paper E 的 F8 轨道纹理（Y_l^m 在 FS 上的分布）原则上可被 QPI 测出
- 但 QPI 的 q 空间分辨率不足以直接看到轨道纹理（需高分辨 + ARPES 联合）

**A 部分完成总结：**

```
A1 零电阻       ✅ v1.0 (7.3 KB)
A2 Meissner    ✅ v1.0 (7.9 KB)
A3 比热跃变    ✅ v1.0 (8.5 KB)
A4 同位素效应  ✅ v1.0 (10.1 KB)
A5 能隙特征    ✅ v1.0 (10.7 KB)
A6 临界场       ✅ v1.0 (10.0 KB)
A7 临界电流    ✅ v1.0 (8.2 KB)
A8 Strange Metal ✅ v1.0 (9.8 KB)【重点】
A9 Andreev 反射 ✅ v1.0 (6.0 KB)
A10 QPI         ✅ v1.0 (待补 size)
─────────────────────────────────
合计：A 部分 100%（10/10 子课题）
```

**后续：**
- A 部分综述完成
- 启动 B 部分（微观机制）或先迁移现有论文笔记到 MECE 框架
- 优先做 A 部分的整合分析（横跨 A1-A10 寻找经验律）

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。Hoffman 2002 + Hanaguri 2009 + Fischer 2007 RMP 三大文献为核心。**A 部分综述完成**
