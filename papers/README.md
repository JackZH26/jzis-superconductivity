# 精读笔记库 — Papers Reading Notes

**迁移日期：** 2026-04-30
**来源：** `research/papers/library/` + `research/paper-reading/sc/`

---

## 目录结构

```
papers/
├── library/          # 深度精读（手工精读，有 MECE 映射）
│   ├── bozovic_parsed/   # Bozovic 铜氧化物系列 9 篇解析文档
│   └── *.md          # 各论文精读笔记
└── daily/            # 夜间自动精读（2026-04-09 至 04-29，约 118 篇）
```

---

## library/ — 深度精读索引

| 文件 | 论文 | MECE 关联 |
|------|------|-----------|
| `Romero_Planckian-FeTeSe_READING_NOTES.md` | Romero 2026, FeTeSe Planckian 传输 | H1, H2, H8 |
| `Yang_Eu-IL-Nickelate-Reentrant-SC_READING_NOTES.md` | Yang 2026, Eu-NiO₂ 磁场诱导 SC | H7, H9, G5, D5 |
| `Deng_Ambient-151K-Hg1223-PNAS2026_READING_NOTES.md` | Deng 2026, Hg-1223 常压 151K | D3, A6 |
| `Bozovic_Cuprate-Interface-Series_READING_NOTES.md` | Bozovic 铜氧化物界面系列（9 篇） | D3, D11, B9 |
| `Lee_Nd085Sr015NiO2_2026_NOTE.md` | Lee 2026, Nd₀.₈₅Sr₀.₁₅NiO₂ | D5 |
| `Nie_Nickelate-Superstructure_2026_NOTE.md` | Nie 2026, 镍酸盐超结构 | D5 |
| `Bhatt_LNO-Structural-Modifications_Nature2026_NOTE.md` | Bhatt 2026, LNO 结构修饰 | D5 |
| `Bhatt_Structural-Origins-SC-Strain-LNO_2026_NOTE.md` | Bhatt 2026, 应变起源的 LNO 超导 | D5, E4 |
| `Hsu_Fermi-Liquid-LaPrNiO_2026_NOTE.md` | Hsu 2026, La-Pr-NiO₂ Fermi 液体 | D5, H1 |
| `Xiang_La3Ni2O7-Oxygen-Recycling_2026_NOTE.md` | Xiang 2026, La₃Ni₂O₇ 氧循环 | D5 |
| `Shao_CDW-Structural-Chirality_PRL2026_NOTE.md` | Shao 2026, CDW 手性结构 | H4, D14 |
| `Shao_Electric-Field-LNO_2026_NOTE.md` | Shao 2026, LNO 电场调控 | E4, D5 |
| `Levitin_YbRh2Si2-OddParity_2026_NOTE.md` | Levitin 2026, YbRh₂Si₂ 奇宇称 | D8, C6 |
| `Cheng_Frieze-CsCr3Sb5_2026_NOTE.md` | Cheng 2026, CsCr₃Sb₅ Kagome | D14 |
| `Wang_Moire-CPDM_2026_NOTE.md` | Wang 2026, Moiré CPDM | D13 |
| `Wu_CrSbS3-Multiferroic_2026_NOTE.md` | Wu 2026, CrSbS₃ 多铁 | G1, G2 |
| `Xia_WSe2-Mott-SC_Nature2026_NOTE.md` | Xia 2026, WSe₂ Mott-SC | D13, B14 |
| `Zhu_BEC-Infinite-Layer-Cuprate_PRB2025_NOTE.md` | Zhu 2025, BEC 无限层铜氧化物 | D3 |

---

## daily/ — 夜间自动精读（2026-04-09 至 04-29）

共 118 篇，每篇约 1-3KB，格式为 `YYYY-MM-DD_first-author-topic.md`

主要覆盖方向：
- **镍酸盐（La₃Ni₂O₇/无限层）**：约 30 篇（pairing/band/structure/transport）
- **氢化物超导**：约 20 篇（SSCHA/anharmonic/isotope/ternary）
- **铜氧化物**：约 15 篇（pseudogap/Planckian/NMR/CDW）
- **平坦带/量子几何**：约 10 篇（Peotta-Törmä/MATBG/Kagome）
- **铁基/FeSe**：约 8 篇（FeSe-STO/nematic/multi-channel）
- **有机/富勒烯**：约 5 篇（κ-ET/K₃C₆₀）
- **拓扑/非中心对称**：约 5 篇
- **其他（重费米子/磁性/界面）**：约 25 篇

---

## 使用说明

1. library/ 笔记与 MECE 章节直接对应，可作为各章节的"数据核查"来源
2. daily/ 笔记是快速精读摘要，可按方向筛选后补充到对应 MECE 章节的参考文献
3. 数据核查原则：实验数值以原始论文 DOI 为准，代码中的数值不算来源
