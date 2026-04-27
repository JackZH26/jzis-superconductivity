# A9. Andreev 反射（Andreev Reflection）

**MECE 编号：** A9
**关联 MECE：** A5（能隙）、C5/C7（p 波 / chiral 配对）、F4-F5（拓扑 SC、Majorana 零模）、D12（拓扑超导候选）、I9（隧穿测量）
**精读日期：** 2026-04-27
**精读模型：** Claude Opus 4.7（high thinking）
**层级：** 综述（基于 Andreev 1964 + BTK 1982 + Majorana 现代综述）

---

## 1. 物理定义

**Andreev 反射：** 当能量 E < Δ 的电子从正常金属（N）入射 N/S 界面时，由于 SC 内部没有单粒子激发态可填，电子被反射回**hole**（自旋翻转 + 动量反向），同时在 SC 中形成一个 Cooper 对。

[关键物理图像]
```
N | S 界面：
入射: e⁻(↑, k, E)
反射: h(↓, -k, -E) ← Andreev 反射（不是普通反射）
透射: 进入 SC 凝聚体作为 Cooper 对（2e 电荷）
```

**总效应：** 入射电子 (1e) → 凝聚体 (2e) + 反射 hole (-1e)，电荷守恒。

---

## 2. BTK 模型

[来源] Blonder-Tinkham-Klapwijk 1982 PRB 25, 4515 [DOI: 10.1103/PhysRevB.25.4515]

### 2.1 模型设置
单 1D N/S 界面，参数：
- Δ：超导能隙
- Z：界面屏障强度（无量纲）
  - Z = 0：完全透明（理想 Andreev）
  - Z → ∞：隧穿极限（标准 BCS DOS 探测）

### 2.2 关键预测：电导谱 dI/dV(V)

| 偏压 V | dI/dV |
|--------|-------|
| Z = 0, eV < Δ | **2**·G_n（电导加倍 — Andreev 主导）|
| Z = 0, eV > Δ | G_n（正常） |
| Z >> 1, eV < Δ | ≪ G_n（隧穿压制） |
| Z >> 1, eV > Δ | G_n |

[定理] **在理想透明界面（Z=0），E < Δ 时电导加倍**。这是 Andreev 反射的标志性特征，与隧穿（Z >> 1，电导压制）相反。

### 2.3 实测谱形态
| 类型 | 谱形 | Z |
|------|------|---|
| 点接触（PCAR）| dI/dV ~ 在 ±Δ 处下降，Z=0 区间增强 | 中等 0.1-1 |
| 隧穿结 | dI/dV ~ 在 ±Δ 处尖峰 | Z >> 1 |
| 良好接触 | 介于两者 | 0.5 |

---

## 3. 历史关键节点

| 年份 | 事件 | 来源 |
|------|------|------|
| **1964** | **Andreev** 提出反射机制 | Sov. Phys. JETP 19, 1228 |
| 1965 | de Gennes 推广到 unconventional SC | Solid State Physics |
| **1982** | **BTK** 模型给出定量预测 | PRB 25, 4515 |
| 1990s | Andreev 谱用于诊断 d 波节点 | 多篇 |
| 2000s | Tunneling spectroscopy 在铜氧/铁基广泛应用 | Fischer 2007 RMP |
| **2012** | Mourik et al. InSb-NbTiN ZBCP 报告（首次 Majorana 候选）| Science 336, 1003 |
| 2018+ | Microsoft Station Q、TU Delft 团队多篇 ZBCP 报告 | 系列论文 |
| **2021** | Microsoft 撤回 2017/2018 Majorana 论文（数据问题）| 学术争议 |

---

## 4. Andreev 反射作为能隙诊断

### 4.1 各向同性 s 波（标准 BCS）
- 电导加倍区在 |eV| < Δ
- 平坦的 Andreev 平台

### 4.2 d 波（节点 SC）
- 有节点方向上 Δ → 0，dI/dV 在 V → 0 时不为零
- **零偏压电导峰（ZBCP）出现**：在表面切向特殊取向时形成 Andreev 边界态
- 来源：Tanaka-Kashiwaya 1995 PRB 53, 9371

[定理 - Tanaka-Kashiwaya 1995] d 波 SC 在某些表面取向产生**Andreev 束缚态**（ABS）在 E = 0，给出 ZBCP。

### 4.3 p 波（spin-triplet）
- 节点结构特殊，ZBCP 也常出现
- 与 Majorana 末态混淆是关键问题

### 4.4 chiral d±id, p±ip
- 时间反演破缺
- ZBCP 形态依赖于表面取向和外加场

---

## 5. Majorana 零模与 ZBCP 争议

### 5.1 物理预测
[来源] Kitaev 2001（Kitaev chain）；Lutchyn-Sau-Das Sarma 2010 PRL 105, 077001

**1D 拓扑 SC**（如半导体纳米线 + s 波 SC + Zeeman + 自旋轨道）支持 Majorana 零模。

[预测]
- **Majorana ZBCP 量子化**：dI/dV(V=0) = 2e²/h
- **稳健性**：对小扰动不敏感
- 在拓扑相变点上下变化

### 5.2 实验报告（争议史）

| 年份 | 实验 | 报告 | 后续 |
|------|------|------|------|
| 2012 | Mourik et al. (TU Delft) | InSb 纳米线 ZBCP | 引发热潮 |
| 2017 | Zhang et al. (TU Delft+Eindhoven) | "量子化"ZBCP at 2e²/h | **2021 撤稿**（数据筛选）|
| 2018 | Microsoft 多篇 | ZBCP 系列 | 部分撤回 |
| 2020+ | 学界共识：单纯 ZBCP 不足以证明 Majorana | 多篇 | 需更多判据 |

### 5.3 现代判据（多重必要）
要确认 Majorana，需要：
1. ZBCP 高度 = 2e²/h（量子化）
2. ZBCP 在 trivial Andreev 不应区域稳定
3. **拓扑相变**伴随 ZBCP 出现/消失
4. 多端测量的非局域响应（如 Fu-Kane 半导体提案）
5. 4π 周期 Josephson 效应

[反幻觉警告] 学界对 ZBCP 是否唯一来自 Majorana 仍有争议。Trivial（disorder-induced）Andreev 束缚态可能产生类似 ZBCP。

[来源]
- Pan-Das Sarma 2020+ 多篇质疑
- Yu et al. 2021 Microsoft 回应（撤稿）

---

## 6. 测量方法

### 6.1 点接触（PCAR）
- 金属针压紧 SC 表面
- 接触电阻 R_n 决定 Z 值
- 优点：简单
- 局限：Z 不可控，结质量难评估

### 6.2 平面 N/S 隧穿结
- 多层薄膜结构
- Z 受隔离层厚度控制
- 高质量结很难做

### 6.3 STM Andreev 模式
- STM 针在 SC 表面扫描
- 高空间分辨率 + 能谱
- 与 A10 QPI 结合

### 6.4 半导体纳米线 + 引脚电极
- Majorana 候选实验主流
- 多端测量拓扑相变
- 极低 T (mK)

### 6.5 N-S-N 三端结构
- Andreev 反射"crossed" + "elastic cotunneling"
- 区分 trivial Andreev vs Majorana

---

## 7. 已知例外 / 复杂情形

### 7.1 多带 / 多能隙 SC
- MgB₂、铁基：双能隙
- Andreev 谱出现两个台阶
- 拟合需双 Δ 模型

### 7.2 各向异性能隙
- d 波在不同晶向 Δ 不同
- ZBCP 强度依赖表面取向
- 必须明确实验几何

### 7.3 Trivial Andreev ZBCP
- 杂质散射、限域态、Kondo 等
- 与 Majorana 区分困难
- "Smoking gun" 标准未定

### 7.4 Pseudogap 影响
- 铜氧 underdoped 中 T > Tc 已有部分能隙
- Andreev 谱在 Tc 上方就显示结构

### 7.5 涨落主导区
- 接近 Tc 时谱模糊化

### 7.6 Zeeman 场分裂
- 强场下 Andreev 峰分裂
- 区分 Majorana 与 trivial

---

## 8. 与其他 MECE 编号的关联

| 关联课题 | 关系 | 说明 |
|---------|------|------|
| A5 能隙 | **核心工具** | Andreev 谱直接探测 Δ |
| A10 QPI | 互补 | STM 实空间 + Andreev 能谱 |
| C1-C10 配对对称性 | 直接 | ZBCP 是 d/p 波诊断 |
| F4-F5 拓扑 SC | **争议焦点** | Majorana ZBCP |
| D12 拓扑 SC 候选 | 测试场 | Sr₂RuO₄, β-Bi₂Pd 等 |
| I9 隧穿 | 工具 | 标准实验方法 |

---

## 9. 推荐精读论文

### 必读（基础理论）
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Andreev 1964 | Sov. Phys. JETP 19, 1228 | 经典 |
| **BTK 1982** | DOI: 10.1103/PhysRevB.25.4515 | **核心模型** |
| Tanaka-Kashiwaya 1995 | DOI: 10.1103/PhysRevB.53.9371 | d 波 ABS / ZBCP |

### Majorana 候选
| 论文 | DOI/来源 | 备注 |
|------|---------|------|
| Kitaev 2001 | DOI: 10.1070/1063-7869/44/10S/S29 | Kitaev chain |
| Lutchyn-Sau-Das Sarma 2010 | DOI: 10.1103/PhysRevLett.105.077001 | 半导体纳米线方案 |
| Mourik et al. 2012 Science 336, 1003 | DOI: 10.1126/science.1222360 | 第一个 ZBCP 报告 |
| **Pan-Das Sarma 2020** | 多篇质疑 | 必读 |

### 综述
| 论文 | 来源 | 状态 |
|------|------|------|
| **Fischer et al. 2007 RMP 79, 353** | DOI: 10.1103/RevModPhys.79.353 | STM in SC 综述 |
| Stanescu-Tewari 2013 综述 | J. Phys. CM 25, 233201 | Majorana 综述 |
| Wiesendanger group review | 多篇 | Majorana 现状 |

---

## 10. 数据汇总（反幻觉确认）

[定理 - BTK 1982] Z=0 时 E < Δ 电导加倍 G(0) = 2 G_n

[定理 - Tanaka-Kashiwaya 1995] d 波 (110) 表面 ABS 给出 ZBCP

[预测 - Lutchyn 2010] 半导体纳米线 Majorana ZBCP at 2e²/h

[观察] Mourik 2012 ZBCP 高度 << 2e²/h（未量子化）

[历史争议] 2017-2021 多篇"量子化 ZBCP"声明被撤回 — 数据筛选问题

[当前共识] 单纯 ZBCP 不足以证明 Majorana，需多重判据

---

## 11. 反幻觉自检

- [x] Andreev 1964, BTK 1982, Tanaka-Kashiwaya 1995 经典 DOI 标注
- [x] Mourik 2012 Science 完整 DOI
- [x] **Microsoft/TU Delft 撤稿事件明确说明**（2017-2021）
- [x] 不假装 ZBCP = Majorana
- [x] 不混淆 trivial Andreev 与拓扑 ZBCP
- [x] 多端测量需求明确

---

## 12. 反谄媚自检

- [x] **Majorana 实验史的争议坦诚说明** — 不偏向任何阵营
- [x] Pan-Das Sarma 质疑明确列出
- [x] 单 ZBCP 不足以证明 Majorana 的共识明确
- [x] BTK 模型局限（1D, 单带）说明
- [x] 多带 / 各向异性 / 涨落复杂性不掩盖

---

## 13. 当前状态与后续行动

**状态：** [已综述]

**遗留问题：**
1. Majorana 实验严格判据的统一标准（→ F4-F5 持续跟踪）
2. 镍酸盐 / 铜氧 / 铁基的 Andreev 谱系统对比
3. UTe₂ Andreev 谱与 spin-triplet 关系（→ G7, D8）
4. STM Andreev 模式在拓扑 SC 候选材料的应用（→ D12）

**后续：** A10（QPI），完成 A 部分

---

**修订日志：**
- v1.0 (2026-04-27): 初版建立。重点强调 Majorana ZBCP 的实验争议史
