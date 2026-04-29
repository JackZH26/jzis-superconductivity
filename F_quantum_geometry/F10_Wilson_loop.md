# F10. Wilson Loop（Wilson 圈）— 量子几何框架中最通用的拓扑不变量计算工具

**MECE 编号：** F10
**关联 MECE：**
- F2（Berry 曲率 — Berry 联络矩阵 A(k) 是 Wilson loop 的核心输入；F2 侧重曲率本身，F10 侧重联络的路径有序积分）
- F3（Chern 数 — Wilson loop 本征值的绕数 = Chern 数；F3 侧重定义和分类，F10 提供数值计算的实操工具）
- F1（量子度规 — 量子几何张量 QGT 的另一半；F1 是对称部分 g_mn，F10 的 Wilson loop 依赖反对称部分 Berry 联络 A）
- B11（拓扑超导 — Wilson loop 作为 BdG 哈密顿量拓扑不变量的计算工具；Class D/DIII 的 Chern 数/Z₂ 均可通过 BdG Wilson loop 求得）

**层级关系：** F10 是 F2（Berry 联络）→ F3（Chern 数）→ F10（Wilson loop 计算工具）这条链上的终点。F2 定义了 Berry 联络 A(k)；F3 告诉我们 Chern 数 = (1/2π)∫Ω d²k；F10 给出在数值计算中如何用离散 k 格点的重叠矩阵乘积（Wilson loop）规范不变地计算 Chern 数和 Z₂ 不变量。同时，F10 的 Wannier 函数中心解释把 Berry 相（F2 的内容）与物理可观测量（电极化）直接联系起来。
**精读日期：** 2026-04-29
**精读模型：** Claude Sonnet 4.6（high thinking）
**层级：** 综述（Wilson loop 数学定义 / 历史关键节点 / Chern 数计算 / Z₂ 不变量 / Wannier 函数中心 / 数值实操方法 / BdG 超导应用 / Zak 相 / 关键定量数据 / 反谄媚 / 未解问题）

---

## 1. 物理定义与核心思想

### 1.1 Wilson Loop 的数学定义（[定理]）

```
=== Wilson Loop：Berry 联络的路径有序积分 [定理] ===

Berry 联络矩阵（多带情况，m,n = 占据带指标，[定理]）：

  LaTeX: [A_\mu]_{mn}(\mathbf{k}) = \langle u_m(\mathbf{k}) | i\partial_{k_\mu} | u_n(\mathbf{k}) \rangle

  ASCII: [A_mu]_mn(k) = <u_m(k) | i * ∂_{k_mu} | u_n(k)>

  其中：
    u_m(k) = 第 m 个占据 Bloch 态的晶格周期部分
    ∂_{k_mu} = 沿 k_mu 方向的偏导数（mu = x, y, z）
    m, n 遍历所有占据带（多带情况 → A 是矩阵）

Wilson loop 矩阵（路径有序积分，[定理]）：

  LaTeX: W_C = \mathcal{P}\exp\!\left(i\oint_C \mathbf{A}(\mathbf{k})\cdot d\mathbf{k}\right)

  ASCII: W_C = P * exp( i * ∮_C A(k) · dk )

  其中：
    C = k 空间中的封闭路径（必须是回到出发点的闭合曲线）
    P = 路径有序算符（Path-ordered，多带情况不可省略！）
    A(k) · dk = [A_mu]_mn * dk_mu（矩阵缩并）
    W_C ∈ U(N)（N = 占据带数目，幺正矩阵）

  ⚠️ 路径有序为什么关键（[定理，非阿贝尔 Berry 联络]）：
    → 多带情况：A(k) 是 N×N 矩阵，矩阵乘法不可对易
    → P 表示沿路径 k₁ → k₂ → ... → k_N：靠近 k₁ 的矩阵放在最右边（时间排序）
    → 若忽略 P（单纯普通积分），多带时结果错误
    → 单带（N=1）：A(k) 是标量 → P 无影响 → 可以忽略 P

单带（N=1）Wilson loop 简化（[定理]）：

  LaTeX: W_C = \exp\!\left(i\oint_C A(\mathbf{k})\,dk\right) = e^{i\gamma}

  ASCII: W_C = exp( i * ∮_C A(k) dk ) = e^{i*gamma}

  其中：
    gamma = ∮_C A(k) dk = Berry 相（与 F2 的 Berry 相完全一致）
    |W_C| = 1（幺正性，因为 A(k) 是实数场）

物理解读：
  → 单带：Wilson loop = 携带 Berry 相的相位因子（Berry 相的指数）
  → 多带：Wilson loop = 幺正矩阵，本征值 {e^{i*theta_j}} 包含更丰富的拓扑信息
  → Wilson loop 是比 Berry 相更通用的工具：单带时退化为 Berry 相，多带时升级为矩阵
```

### 1.2 规范不变性（[定理]）

```
=== Wilson Loop 的规范结构：哪些量是物理可观测的 [定理] ===

规范变换下的行为（[定理]）：
  Bloch 态规范变换：|u_n(k)⟩ → e^{i*phi_n(k)} |u_n(k)⟩
  Berry 联络变换：A(k) → U†(k) A(k) U(k) + U†(k) i * ∂_k U(k)
  （U(k) = 对角幺正矩阵，多带情况为一般幺正矩阵）

Wilson loop 矩阵的变换：
  W_C → U†(k₀) W_C U(k₀)（相似变换，k₀ = 路径起点）

规范不变量（[定理]）：
  ✅ det(W_C) = det(e^{i*sum_j theta_j}) → 规范不变（相似变换不改变行列式）
  ✅ 本征值 {e^{i*theta_j}} → 规范不变（相似变换不改变本征值）
  ✅ θ_j（Wannier 中心相位） → 规范不变
  ❌ W_C 矩阵本身 → 规范依赖（受 U(k₀) 相似变换影响）

物理后果：
  → 只有 W_C 的行列式相位和本征值相位（θ_j）有物理意义
  → 单带 Berry 相 γ = arg(W_C) = arg(e^{i*gamma}) → 规范不变（mod 2π）
  → Chern 数通过 θ_j(k) 的绕数计算 → 规范不变整数
  → Z₂ 不变量通过 θ_j 在 TRIM 处的奇偶性 → 规范不变整数
```

---

## 2. 历史关键节点

```
=== Wilson Loop 的历史发展：从粒子物理到凝聚态 ===

[1974] Kenneth Wilson（格点规范理论，[来源待验证]）：
  → 提出"Wilson loop"概念：规范场沿封闭路径的路径有序积分
  → 原始目的：格点 QCD 中强相互作用的强耦合展开
  → W_C = P * exp(i * ∮ A_mu dx^mu)（形式完全相同！）
  → Nobel 物理奖 1982（格点规范理论）
  ⚠️ [来源待验证]：K. Wilson, Phys. Rev. D 10, 2445 (1974)，细节待核实

[1984] Michael Berry（单带 Berry 相，[确定]）：
  → Berry, M.V., Proc. R. Soc. A 392, 45 (1984)（确定引用）
  → 绝热演化下几何相位 γ = ∮ A · dk（固体物理中：单带 Wilson loop 的相位！）
  → 奠定了单带 Wilson loop（e^{i*gamma}）与可观测量的联系
  → ⚠️ Berry 1984 是 F10 唯一**确定**来源

[1989] J. Zak（固体中的 Zak 相，[来源待验证]）：
  → Zak, J., Phys. Rev. Lett. 62, 2747 (1989)（引用细节待核实）
  → 定义了 1D 晶体 BZ 上的 Berry 相（"Zak 相"）
  → γ_Zak = ∮_BZ A(k) dk（1D BZ 封闭路径的 Wilson loop 相位）
  → Zak 相量子化（空间反演对称性下）：γ_Zak = 0 or π
  ⚠️ [来源待验证]：PRL 62, 2747 引用细节需原始论文核实

[1993] King-Smith & Vanderbilt（现代极化理论，[来源待验证]）：
  → King-Smith, R.D.; Vanderbilt, D., Phys. Rev. B 47, 1651 (1993)（细节待核实）
  → 电极化 P = e * ∑_j Wannier 中心 = e * ∑_j (Berry 相/2π)
  → 将 Wilson loop 的相位（Wannier 中心）与宏观可观测量（电极化）直接联系
  → 奠定了 Wilson loop 在凝聚态物理中的核心地位
  ⚠️ [来源待验证]：PRB 47, 1651 引用细节需原始论文核实

[2011] Yu et al. / Soluyanov & Vanderbilt（多带 Wilson loop 计算 Z₂，[来源待验证]）：
  → Yu, R. et al., Phys. Rev. B 84, 075119 (2011)（细节待核实）
  → Soluyanov, A.A.; Vanderbilt, D., Phys. Rev. B 83, 235401 (2011)（细节待核实）
  → 系统化了用 Wilson loop 本征值（Wannier 中心）计算 Z₂ 拓扑不变量的数值方法
  → 绕开了繁琐的规范选取问题，成为数值计算 Z₂ 的主流方法
  ⚠️ [来源待验证]：两篇引用细节均待核实

[2017+] Z₂Pack 软件（[来源待验证]）：
  → Gresch, D. et al., Phys. Rev. B 95, 075146 (2017)（细节待核实）
  → 自动化计算 Wilson loop / Wannier 中心 / Z₂ / Chern 数的 Python 软件包
  → 目前凝聚态拓扑不变量数值计算的标准工具之一
  ⚠️ [来源待验证]：引用细节待核实

[2017+] WannierTools 软件（[来源待验证]）：
  → Wu, Q. et al., Comput. Phys. Commun. 224, 405 (2018)（细节待核实）
  → 拓扑不变量 + 表面态 + Fermi 弧的综合计算软件
  → 内部实现也用 Wilson loop / 重叠矩阵方法
  ⚠️ [来源待验证]：引用细节待核实

[2010s+] BdG Wilson loop 与拓扑超导（[多来源，来源待验证]）：
  → 将 Wilson loop 方法推广到 BdG（Bogoliubov-de Gennes）哈密顿量
  → Class D：BdG Wilson loop 绕数 = Chern 数
  → Class DIII：BdG Wilson loop 的 Pfaffian → Z₂（F5 关联）
  → 成为拓扑超导数值表征的核心工具
```

---

## 3. Wilson Loop 的物理意义（多个应用）

### 3.1 计算 Chern 数（[定理]）

```
=== 用 Wilson Loop 绕数计算 Chern 数：数值算法 [定理] ===

算法思路（[定理，基于 F3 Chern 数的等价表达]）：
  1. 固定 ky，沿 kx 方向计算 1D Wilson loop W(ky)：
     W(ky) = P * exp( i * ∫_{kx=0}^{2π} A_x(kx, ky) dkx )（封闭路径）

  2. 求 W(ky) 的本征值 {e^{i*theta_j(ky)}}：
     theta_j(ky) = Wilson loop 本征值的相位（Wannier 中心，j = 带指标）

  3. 随 ky 从 0 到 2π 扫描：追踪 theta_j(ky) 的演化

  4. Chern 数 = theta_j 的总绕数（绕 ky 一圈后 θ 累计增加几个 2π）：

     LaTeX: C = \frac{1}{2\pi}\sum_j \oint_0^{2\pi} \partial_{k_y}\theta_j(k_y)\,dk_y

     ASCII: C = (1/2pi) * Σ_j ∫_0^{2pi} ∂_{ky} θ_j(ky) dky

     → C ∈ Z（整数，由 θ_j 的周期性保证）
     → C > 0：Wannier 中心整体向右移动 C 格
     → C < 0：Wannier 中心整体向左移动 |C| 格

物理解读（Wannier 中心 ↔ Chern 数，[定理]）：
  → θ_j(ky) = 第 j 个占据态 Wannier 函数沿 x 方向的中心位置（以晶格常数为单位）
  → Chern 数 C = ky 扫一圈后所有 Wannier 中心的净位移（整数格）
  → C ≠ 0 → Wannier 中心不能都被"锁定"在某个值（拓扑障碍）
  → 对应实空间的量子化 Hall 电导：σ_xy = C * e²/h（TKNN 公式，F3 关联）

数值实现（[定理，规范不变离散方法]）：
  → 对 ky 取 M 个格点：ky_i = i * 2π/M（i = 0, 1, ..., M-1）
  → 每个 ky_i：取 N 个 kx 格点，计算 W(ky_i)（见第 5 节离散方法）
  → 提取 θ_j(ky_i)，追踪相位连续性，最后计算总绕数
  → 绕数必须是整数（否则说明 N 或 M 太小，需要增大格点数）
```

### 3.2 Z₂ 不变量（Class AII / DIII，[定理]）

```
=== Wilson Loop 计算 Z₂ 不变量：时间反演不变体系 [定理] ===

物理背景（[定理，F3/B11 关联]）：
  → Class AII（时间反演 T, T²=-1）：拓扑绝缘体，Z₂ 不变量
  → Class DIII（T + PHS，T²=-1）：时间反演不变拓扑超导，Z₂ 不变量
  → 时间反演对称性（TRS）：T W_C T⁻¹ = W_C*（Wilson loop 的复共轭）
  → 在时间反演不变动量（TRIM，k = -k mod G）处，TRS 强制约束

Z₂ 不变量的 Wilson loop 计算方法（[定理，基于 Yu et al. 2011，来源待验证]）：
  → 在 BZ 的一半（k_y ∈ [0, π]）计算 Wilson loop 本征值 θ_j(ky)
  → TRIM 处（ky = 0 和 ky = π）：Kramers 简并 → θ_j 成对出现（±）
  → 追踪 θ_j(ky) 从 ky = 0 到 ky = π 的演化
  → Z₂ 不变量 ν：

     ν = 0（平庸）：θ_j 配对不切换（相同指标的本征值回到同一"槽"）
     ν = 1（拓扑）：θ_j 配对切换（奇数次交叉 → 拓扑非平庸）

奇偶性判据（等价表达，[定理]）：
  → ν = 1 当且仅当 θ_j 在 ky = 0 → π 过程中发生奇数次交叉（相位轨迹缠绕）
  → 类比：Pfaffian 方法（F5 Kitaev chain）= Wilson loop 绕数的特殊情况

Kramers 简并保护（[定理]）：
  → TRS（T²=-1）：每个 k 点能带至少两重简并（Kramers 对）
  → Wilson loop 本征值 θ_j 在 TRIM 处严格两两配对
  → 配对模式的切换 = Z₂ 的拓扑信息，不依赖具体基选取（规范不变！）
```

### 3.3 Wannier 函数中心（[定理，King-Smith-Vanderbilt，来源待验证]）

```
=== Wannier 中心与现代极化理论 [定理，King-Smith-Vanderbilt] ===

Wannier 函数定义（[定理]）：
  → Bloch 态 |u_n(k)⟩ 的 Fourier 变换 → Wannier 函数 w_n(r)
  → Wannier 函数在实空间局域（指数衰减），描述化学键

Wannier 中心（[定理]）：
  → 第 j 个 Wannier 函数的中心 ⟨r_j⟩ = Berry 相 / 2π × 晶格常数：

     LaTeX: \langle r_j \rangle = \frac{a}{2\pi}\,\theta_j

     ASCII: <r_j> = (a/2pi) * θ_j（a = 晶格常数）

  → θ_j = Wilson loop W_C 的第 j 个本征值的相位
  → Wannier 中心 ∈ [0, a)（在晶胞内，由 Berry 相的 mod 2π 性质决定）

现代极化理论（[定理，King-Smith-Vanderbilt，来源待验证]）：
  → 宏观电极化 P（电偶极矩密度）：

     LaTeX: P = \frac{e}{\Omega}\sum_j \langle r_j \rangle = \frac{e}{\Omega}\sum_j \frac{a}{2\pi}\,\theta_j

     ASCII: P = (e/Omega) * Σ_j <r_j> = (e/Omega) * Σ_j (a/2pi) * θ_j

  → Omega = 晶胞体积，e = 电子电荷
  → P 可以通过 Wilson loop 本征值直接计算！（非定域 Bloch 态无法直接算 P）
  → P 的量子化歧义：θ_j 有 2π 整数倍的规范不定性 → P 有 e*a/Omega 的量子化歧义
     （但 ΔP 即极化变化是无歧义的——拓扑意义）

拓扑不变性（[定理]）：
  → 在绝热（连续）形变过程中，Wannier 中心只能移动整格（因为 θ_j 只移动 2π 整数倍）
  → C ≠ 0 → 在某种形变下，Wannier 中心无法连续回到出发点（拓扑障碍）
  → 拓扑绝缘体的 Wannier 中心分布与平庸绝缘体本质不同（不能绝热相连）
```

---

## 4. 数值计算 Wilson Loop（实操方法）

### 4.1 离散 k 格点方法（规范不变，[定理]）

```
=== 离散重叠矩阵法：数值计算 Wilson Loop 的标准方法 [定理] ===

核心想法（[定理，规范不变离散方法]）：
  → 直接用路径有序积分 → 需要规范；不方便数值实现
  → 改用相邻 k 点之间 Bloch 态的重叠矩阵 → 规范不变！

重叠矩阵定义（[定理]）：
  → 路径上相邻两点 k_i 和 k_{i+1} 之间的重叠矩阵：

     LaTeX: [M(k_i, k_{i+1})]_{mn} = \langle u_m(k_i)\,|\,u_n(k_{i+1})\rangle

     ASCII: M_mn(k_i, k_{i+1}) = <u_m(k_i) | u_n(k_{i+1})>（m, n = 带指标）

  → M 是 N×N 复矩阵（N = 占据带数）

离散 Wilson loop 矩阵（路径有序矩阵乘积，[定理]）：
  → 路径：k₁ → k₂ → ... → k_K → k₁（K 个格点，封闭路径）

     LaTeX: W = M(k_1, k_2)\cdot M(k_2, k_3)\cdots M(k_{K-1}, k_K)\cdot M(k_K, k_1)

     ASCII: W = M(k_1,k_2) * M(k_2,k_3) * ... * M(k_{K-1},k_K) * M(k_K,k_1)

     → 矩阵乘积（注意顺序！路径有序的离散版本）
     → W ≈ U(N)（有限 K 时近似幺正；K → ∞ 时精确幺正）

规范不变性证明（[定理]）：
  → 规范变换：|u_m(k_i)⟩ → Σ_n V_mn(k_i) |u_n(k_i)⟩（V(k_i) ∈ U(N)）
  → 变换后：M(k_i, k_{i+1}) → V†(k_i) * M(k_i, k_{i+1}) * V(k_{i+1})
  → 矩阵乘积（封闭路径）：W → V†(k₁) * W * V(k₁)（相似变换）
  → 本征值不变 ✅（相似变换的本征值不变）
  → Chern 数 / Z₂ 通过本征值计算 → 完全规范不变 ✅

数值流程（实操，[定理]）：
  1. 从第一性原理（DFT / tight-binding）或模型获得 |u_m(k_i)⟩
  2. 构建所有相邻 k 点的重叠矩阵 M(k_i, k_{i+1})
  3. 计算矩阵乘积 W（K = 50~200 格点通常足够）
  4. 对 W 进行奇异值分解（SVD）→ 近幺正化（消除数值误差）
  5. 求 W 的本征值 {e^{i*θ_j}}，提取 θ_j（Wannier 中心相位）
  6. 对多个 1D Wilson loop（扫描 ky）重复步骤 2-5
  7. 追踪 θ_j(ky) 的演化，计算绕数（Chern 数）或奇偶性（Z₂）

收敛性与精度（[定理级估算]）：
  → K（路径格点数）越大 → W 越接近精确幺正矩阵 → 精度越高
  → 典型收敛：K = 50 时误差 ~10⁻³；K = 200 时误差 ~10⁻⁵
  → Chern 数为整数 → 只需 W 本征值的绕数，对 K 不太敏感（整数！）
  → Z₂ 为 Z₂ 值（0 or 1）→ 更鲁棒
  ⚠️ [来源待验证]：具体收敛数字来自文献惯例，精确量化待核实
```

### 4.2 Z₂Pack 与 WannierTools（[来源待验证]）

```
=== 主流数值工具简介 ===

Z₂Pack（[来源待验证，Gresch et al. 2017]）：
  → Python 包，自动计算 Wilson loop / Wannier 中心 / Chern 数 / Z₂
  → 接口：tight-binding 模型 / Wannier90 输出 / DFT 软件（VASP, Quantum ESPRESSO 等）
  → 核心算法：离散重叠矩阵法（4.1 节），自动追踪相位连续性
  → 自动处理相位歧义（"轨道追踪"）
  ⚠️ [来源待验证]：Gresch, D. et al., PRB 95, 075146 (2017) 细节待核实

WannierTools（[来源待验证，Wu et al. 2018]）：
  → Fortran/Python 程序，计算拓扑不变量 + 表面态 + Fermi 弧
  → 输入：Wannier90 的 tight-binding 哈密顿量（_hr.dat 文件）
  → 内部实现：Wilson loop 方法 + 迭代 Green 函数（表面态）
  ⚠️ [来源待验证]：Wu, Q. et al., CPC 224, 405 (2018) 细节待核实

两种工具的比较：
  属性                Z₂Pack                    WannierTools
  ────────────────────────────────────────────────────────────
  语言                Python                     Fortran + Python
  Wilson loop 追踪    自动（光滑连续算法）       手动或半自动
  DFT 接口            强（VASP/QE 直接读取）     通过 Wannier90 间接
  表面态              无（纯体块拓扑）           有（Fermi 弧、表面带）
  典型用途            快速拓扑不变量计算         完整拓扑表征（体+面）
  ⚠️ [来源待验证]：比较基于软件文档，精确特性随版本变化
```

---

## 5. Wilson Loop 与超导（BdG 系统）

```
=== BdG 哈密顿量的 Wilson Loop：拓扑超导表征 ===

BdG Wilson loop 的定义（[定理]）：
  → BdG 哈密顿量 H_BdG(k) 定义在 Nambu 空间（粒子+空穴）
  → 与普通能带 Wilson loop 形式完全相同：
     W_C^{BdG} = P * exp( i * ∮_C A^{BdG}(k) · dk )
  → 只是 |u_m(k)⟩ 换成 BdG 占据态（准粒子态）

  ⚠️ BdG 的特殊性：粒子-空穴对称性（PHS，C²= ±1）
     → PHS 对 W_C^{BdG} 施加约束，限制本征值的形式
     → Class D（C²=+1）：W_C 的本征值成对出现（e^{iθ} 与 e^{-iθ}）
     → Class DIII（C²=+1, T²=-1）：Wilson loop 本征值还有时间反演约束

Class D（手性 p+ip 超导，[定理]）：
  → 2D BdG Wilson loop 绕数 = BdG Chern 数 C_BdG（与 F3 定义一致）
  → C_BdG = 1 → 有拓扑边缘态（手性 Majorana 边缘模式）
  → 实例：chiral p+ip SC（如预期的 Sr₂RuO₄，见 F8 注意事项）：
     C_BdG = 1 → 在磁通漩涡核心出现 Majorana 零模（F5 关联）
  → 2D Wilson loop 计算方法：与普通 Chern 数完全相同（第 3.1 节算法），只用 BdG 占据态

Class DIII（时间反演不变拓扑超导，[定理]）：
  → 1D Kitaev chain：1D Wilson loop = Pfaffian[A]（A = BdG 哈密顿量，见 F4）
  → Z₂ 不变量：W = +1（平庸）or W = -1（拓扑，有 Majorana 端模）

     ASCII: nu = Pf[A(pi)] / Pf[A(0)] = ±1（Z₂，来源待验证，基于 Kitaev 2001）

  → 直观：1D Wilson loop 沿 k = 0 → π 的相位演化 → Pfaffian 符号改变 = Z₂ 翻转
  ⚠️ [来源待验证]：Kitaev, A.Yu., Phys.-Usp. 44, 131 (2001) 细节待核实

粒子-空穴对称性对 Wilson loop 的约束（[定理]）：
  → BdG PHS：C H_BdG(k) C⁻¹ = -H_BdG(-k)，C 是粒子-空穴变换算符
  → 推论：W_C(-C 变换后) = W_C*（或其他对称关系，取决于 class）
  → Class D：本征值 θ_j 成对出现（θ_j 和 -θ_j）
  → Class DIII：θ_j 既成对（PHS）又成对（TRS → Kramers 简并）
  → 这些约束使 BdG Wilson loop 的拓扑比普通能带 Wilson loop 更受限（只有 Z 或 Z₂，不是任意整数）

实际计算建议（[定理级建议]）：
  → 使用 WannierTools 或自写 tight-binding BdG 代码
  → 用 Nambu 基（(c_k↑, c_k↓, c†_{-k↑}, c†_{-k↓})）构建 H_BdG
  → 选取"占据"的 BdG 准粒子态（E < 0 的一半）
  → 计算重叠矩阵 → Wilson loop → 本征值绕数 = Chern 数
```

---

## 6. Zak 相（1D Wilson Loop 的特殊情况）

```
=== Zak 相：1D 体系的量子化 Berry 相 ===

定义（[定理，Zak 1989，来源待验证]）：

  LaTeX: \gamma_{\mathrm{Zak}} = \oint_{\mathrm{BZ}} A(k)\,dk \pmod{2\pi}

  ASCII: gamma_Zak = ∮_BZ A(k) dk (mod 2pi)

  其中：
    BZ = 1D 布里渊区（k ∈ [-π/a, π/a]，封闭路径）
    A(k) = Berry 联络（单带，标量）
    gamma_Zak ∈ [0, 2π)（mod 2π，量子化条件见下）

量子化（[定理，需要空间反演对称性]）：
  → 对于有空间反演对称性的 1D 体系：
     gamma_Zak = 0（mod 2π）→ 平庸（trivial）
     gamma_Zak = π（mod 2π）→ 拓扑（topological）
  → 空间反演保护量子化；若无反演对称则 gamma_Zak ∈ 连续值（不量子化）

1D SSH 模型实例（[定理，最经典的 1D 拓扑例子]）：
  → SSH = Su-Schrieffer-Heeger 模型（二聚化 1D 链）
  → 参数 t₁ < t₂（强二聚化）：gamma_Zak = π → 拓扑 → 有端点态
  → 参数 t₁ > t₂（弱二聚化）：gamma_Zak = 0 → 平庸 → 无端点态
  → Bulk-edge correspondence（1D 版本）：
     gamma_Zak = π → 单条边的端点态（1D 版的拓扑边界态）
  → Zak 相 = 1D SSH 中拓扑相与平庸相的判据

1D BdG Kitaev chain（[定理，F4 关联]）：
  → Kitaev chain 的 Z₂ 不变量 = 1D BdG Wilson loop 的相位（Pfaffian 的符号）
  → 拓扑相（μ < 2t）：1D BdG Wilson loop 绕数 = 1（有端 Majorana 零模，F4/F5 关联）
  → 平庸相（μ > 2t）：绕数 = 0
  → Zak 相/1D Wilson loop 是 Kitaev chain 拓扑的同一数学结构的不同语言

与多带 Wilson loop 的关系（[定理]）：
  → 单带：Zak 相 = Wilson loop 的相位 arg(W_C)
  → 多带：多带 Zak 相 = Wilson loop 矩阵 W_C 的行列式的相位 arg(det W_C)
  → det(W_C) = exp(i * Σ_j θ_j) = exp(i * Σ_j Zak 相_j)（带指标求和）
  → 多带 Zak 相 ∈ Z₂（0 or π）当有反演对称时，更通用的是各 θ_j 的 Zak 相

注意歧义（⚠️ 反谄媚）：
  → "Zak 相"有时指单带 gamma_Zak，有时指 W = det 的相位
  → 不同文献定义不统一，阅读时要确认哪种定义！
  → F10 约定：Zak 相 = 单带 1D Wilson loop 的相位（与 Zak 1989 原始定义一致）
```

---

## 7. 关键定量数据

```
=== F10 Wilson Loop 关键数量级与公式 ===

Wilson loop 矩阵的代数性质（[定理，严格]）：
  → W_C ∈ U(N)（近似；精确幺正需要连续极限 K → ∞）
  → 本征值 {e^{i*θ_j}}，θ_j ∈ (-π, π]（相位量纲，实数）
  → 行列式 det(W_C) = exp(i * Σ_j θ_j)（相位求和）

单带 Berry 相范围（[定理]）：
  → γ ∈ [0, 2π)（mod 2π）
  → 在有反演对称的 1D 体系：γ = 0 or π（量子化，[定理]）

Chern 数通过绕数（[定理]）：
  → C ∈ Z（整数）
  → C = (1/2π) * Σ_j ∮ ∂_{ky} θ_j(ky) dky（Wilson loop 本征值绕数）
  → 合理数值：拓扑绝缘体 |C| = 1 or 2（高阶 Chern 更少见）
  → BdG 超导：|C_BdG| = 1 对应一条手性边缘模式（F3/F5 关联）

Z₂ 不变量（[定理]）：
  → ν ∈ {0, 1}（Z₂）
  → ν = 0（平庸）or ν = 1（拓扑）
  → 由 Wilson loop 本征值在 TRIM 处的配对模式确定（奇偶性）

Zak 相量子化（有反演对称，1D，[定理，来源待验证，Zak 1989]）：
  → γ_Zak = 0 or π（精确量子化）

数值精度估算（[来源待验证]）：
  → 典型格点数 K = 100：Wilson loop 矩阵偏离幺正 < 10⁻⁴
  → Z₂Pack 官方文档报告精度：~10⁻⁶（足够分辨整数 Chern 数）
  → Chern 数收敛：K = 50 通常足够（整数，不需要高精度浮点）
  ⚠️ [来源待验证]：上述精度数字来自软件文档和用户经验，非独立推导

重叠矩阵的典型量级（[定理级估算]）：
  → M_mn(k_i, k_{i+1}) ≈ δ_mn - ε * [A_mu]_mn * δk（小间距近似）
  → |1 - M†M| = O(δk²)（每步近似误差，K → ∞ 时消失）
  → δk = 2π / (K * a)（K = 格点数，a = 晶格常数）
```

---

## 8. 关键反谄媚

```
⚠️ 反谄媚 F10.1：Wilson loop 矩阵本身是规范依赖的

  W_C → U†(k₀) W_C U(k₀)（相似变换，依赖路径起点的规范选取）
  物理量 = 本征值 {e^{i*θ_j}} 和 det(W_C)（规范不变！）
  W_C 矩阵本身的矩阵元没有直接物理意义！

  ⚠️ 错误说法："Wilson loop 矩阵 W 就是物理量"
  ✅ 正确说法："Wilson loop 的本征值（Wannier 中心相位 θ_j）是物理量"

⚠️ 反谄媚 F10.2：Wilson loop ≠ Berry 相（单带时才相等）

  单带：W_C = e^{i*gamma}，Wilson loop 的相位 = Berry 相 gamma → ✅ 相等
  多带：W_C 是 N×N 矩阵，包含 N 个本征值 e^{i*θ_j}
         → N 个 θ_j 各不相同（一般情况），信息量远超单个 Berry 相
         → "Berry 相"在多带情况下要看 det(W_C) 的相位（= Σ θ_j），不是单个 θ_j

  ⚠️ 错误推广："多带情况 Berry 相 = Wilson loop 的迹"
  ✅ 正确表述："多带情况 Berry 相的推广 = Wilson loop 行列式的相位（= Σ θ_j）"

⚠️ 反谄媚 F10.3：路径有序（P）在多带情况不可忽略

  多带 Berry 联络 A(k) 是 N×N 矩阵
  → 矩阵乘法不对易：A(k₁) * A(k₂) ≠ A(k₂) * A(k₁)（一般情况下）
  → 路径有序 P = 必须按路径顺序乘矩阵
  → 若忽略 P（用普通积分 e^{i * ∫ tr(A) dk}）：只得到 trace，丢失非阿贝尔结构！

  ⚠️ 错误做法：多带 Wilson loop = exp(i * ∫ tr(A(k)) dk)（只对单带正确）
  ✅ 正确做法：多带 Wilson loop = P * exp(i * ∮ A(k) · dk)（路径有序矩阵指数）

⚠️ 反谄媚 F10.4：数值计算中的相位追踪问题（轨道追踪）

  计算多个 1D Wilson loop W(ky_i)（扫描 ky）时：
  → 每个 ky_i 独立给出本征值 θ_j（j = 1,...,N），但 j 的排序没有自动连续性
  → 相位可以在不同 ky 之间"跳跃"（因为本征值排序可以重新排列）
  → 如果不做"轨道追踪"（smooth continuation / tracking）：
     Chern 数计算会得到错误结果！（绕数因为跳跃被人为抹掉或加倍）

  ⚠️ 解决方法：平滑连续化算法（如 parallel transport gauge / 最大重叠追踪）
  → Z₂Pack 自动处理此问题；手写代码需要显式实现

⚠️ 反谄媚 F10.5：Zak 相的量子化需要空间反演对称性

  有空间反演对称：γ_Zak = 0 or π（量子化，可以作为拓扑判据）
  无空间反演对称：γ_Zak 可以是 [0, 2π) 中任意值（连续，不量子化）
  → γ_Zak ≠ 0 且 γ_Zak ≠ π 的情况不意味着"中间拓扑态"——只是对称性不保护量子化

  ⚠️ 错误推论："测到 γ_Zak = 0.7π → 拓扑性介于 0 和 π 之间"
  ✅ 正确解读："γ_Zak = 0.7π → 没有反演对称保护，不是拓扑相的判据"
```

---

## 9. 未解问题 / 开放前沿

| 问题 | 当前状态（2026-04）| 主要障碍 | 相关 MECE |
|------|---|---|---|
| **强关联体系（MATBG / Kagome SC）Wilson loop 的数值精度** | 部分进展 [来源待验证] | 强关联导致 DFT 不可靠；需要 DMFT/QMC + Berry 联络，计算代价极大 | F10, D10, D11 |
| **BdG Wilson loop 和拓扑超导不变量的系统化计算** | 半成熟 [来源待验证] | BdG 的粒子-空穴空间中规范选取更复杂；Class D/DIII 以外的情况还不完全清楚 | F10, B11, F5 |
| **Wilson loop 的实验直接测量（非间接推断）** | 尚未实现 | Berry 相测量依赖 Aharonov-Bohm 型干涉（只间接反映），完整 Wilson loop 矩阵无直接实验方案 | F10, F2 |
| **开放系统（非厄米）Wilson loop 和拓扑不变量** | 理论进展中 [来源待验证] | 非厄米 Berry 联络不再幺正；Wilson loop 本征值不再在单位圆上；拓扑分类大幅复杂化 | F10, B11 |
| **高阶拓扑绝缘体（HOTI）的 Wilson loop 表征** | 新兴方向 [来源待验证] | 嵌套 Wilson loop（Wilson loop 的 Wilson loop）用于二阶拓扑不变量；数学框架仍在发展中 | F10, F3 |
| **Floquet / 非平衡系统中的 Wilson loop 推广** | 理论提案阶段 [来源待验证] | Floquet 系统中 Wilson loop 的时间依赖性使计算复杂；无统一理论框架 | F10, D10 |
| **Wilson loop 与量子信息（量子计算误差修正）** | 初步探索 [来源待验证] | 非阿贝尔 Wilson loop（Holonomy）可能实现几何量子门；拓扑超导 Majorana 的非阿贝尔统计 | F10, F5, C7 |

---

## 附录：核心速查（ASCII 格式）

```
=== F10 Wilson Loop 核心速查 ===

[1] Berry 联络矩阵 [定理]：
  [A_mu]_mn(k) = <u_m(k) | i * ∂_{k_mu} | u_n(k)>
  m, n = 占据带指标；mu = x, y, z
  多带情况：A(k) 是 N×N 复矩阵（N = 占据带数）

[2] Wilson loop 矩阵 [定理]：
  W_C = P * exp( i * ∮_C A(k) · dk )
  P = 路径有序（多带必须！）
  W_C ∈ U(N)（幺正矩阵）
  单带：W_C = exp(i*γ) = e^{i*gamma}（Berry 相 γ = ∮ A · dk）

[3] 规范不变量 [定理]：
  ✅ 本征值 {e^{i*θ_j}} → 规范不变（物理量！）
  ✅ det(W_C) = exp(i * Σ θ_j) → 规范不变
  ❌ W_C 矩阵本身 → 规范依赖（相似变换 U†WU）

[4] 离散重叠矩阵法 [定理，规范不变]：
  M_mn(k_i, k_{i+1}) = <u_m(k_i) | u_n(k_{i+1})>
  W = M(k_1,k_2) * M(k_2,k_3) * ... * M(k_K,k_1)（矩阵乘积，顺序重要！）
  规范不变：本征值在相似变换下不变

[5] Chern 数计算 [定理]：
  C = (1/2pi) * Σ_j ∫_0^{2pi} ∂_{ky} θ_j(ky) dky
  θ_j(ky) = W(ky) 本征值相位（Wannier 中心）
  C = θ_j(ky) 从 ky=0 到 2π 的总绕数 ∈ Z

[6] Z₂ 不变量（Class AII/DIII）[定理]：
  ky ∈ [0, π]：追踪 θ_j(ky) 的演化
  ν = 0（平庸）：θ_j 配对不交叉（不切换）
  ν = 1（拓扑）：θ_j 奇数次交叉（切换）

[7] Wannier 中心与极化 [定理，King-Smith-Vanderbilt，来源待验证]：
  <r_j> = (a/2pi) * θ_j（Wannier 函数位置 = Wilson loop 本征值相位）
  P = (e/Omega) * Σ_j <r_j>（现代极化理论）
  极化 P 通过 Wilson loop 直接计算，无需波函数的局域化

[8] Zak 相（1D，[定理，Zak 1989，来源待验证]）：
  gamma_Zak = ∮_BZ A(k) dk (mod 2pi)
  有反演对称：gamma_Zak = 0（平庸）or π（拓扑）
  SSH 模型：t₁ < t₂ → γ_Zak = π → 端点态 ✓

[9] BdG Wilson loop [定理]：
  W_C^{BdG} = P * exp(i * ∮ A^{BdG} · dk)（同上，换 BdG 占据态）
  Class D（chiral p+ip）：BdG Wilson loop 绕数 = Chern 数 C_BdG
  Class DIII（Kitaev chain）：1D BdG Wilson loop → Pfaffian → Z₂

[10] 确定来源：
  Berry, M.V. [确定]：Proc. R. Soc. A 392, 45 (1984)
  Zak, J. [来源待验证]：PRL 62, 2747 (1989)
  King-Smith & Vanderbilt [来源待验证]：PRB 47, 1651 (1993)
  Yu et al. [来源待验证]：PRB 84, 075119 (2011)
  Soluyanov & Vanderbilt [来源待验证]：PRB 83, 235401 (2011)
  Gresch et al. (Z₂Pack) [来源待验证]：PRB 95, 075146 (2017)
  Wu et al. (WannierTools) [来源待验证]：CPC 224, 405 (2018)
  Wilson, K.G. [来源待验证]：PRD 10, 2445 (1974)（原始 Wilson loop 定义）

[11] 反谄媚汇总：
  ⚠️ W_C 矩阵规范依赖，只有本征值 {e^{i*θ_j}} 是物理量
  ⚠️ 多带 Wilson loop ≠ Berry 相（W 是矩阵，det W 的相位才是多带 Berry 相）
  ⚠️ 路径有序（P）多带情况不可忽略（非阿贝尔结构！）
  ⚠️ 相位追踪（轨道追踪）不做 → Chern 数计算错误
  ⚠️ Zak 相量子化需要反演对称性，无对称性时不量子化

[12] 层级分类：
  [定理]：Berry 联络矩阵定义；Wilson loop 定义（路径有序积分）；
           规范不变性（本征值）；离散重叠矩阵法；
           Chern 数 = Wilson loop 绕数；Z₂ 奇偶性判据；
           Wannier 中心 = θ_j/(2π) × a；Zak 相定义；
           1D 有反演时 γ_Zak = 0 or π；BdG Wilson loop 形式；
           Class D Chern 数 = BdG Wilson loop 绕数

  [猜想]：高阶拓扑绝缘体的嵌套 Wilson loop；Floquet Wilson loop；
           非厄米 Wilson loop 拓扑；Wilson loop 量子计算应用

  [来源待验证]：所有数值软件（Z₂Pack, WannierTools）；
                 所有引用细节（除 Berry 1984）；
                 King-Smith-Vanderbilt；Zak 1989；
                 Yu et al. 2011；Wilson 1974

[13] MECE 关联图：
  F10（Wilson loop：路径有序积分 + 数值工具）
    ├─ 输入 ← F2（Berry 联络 A(k)：Wilson loop 的被积函数）
    ├─ 输出 → F3（Chern 数：Wilson loop 绕数）
    ├─ 几何基础 ← F1（量子几何张量 QGT：与 Berry 联络的实部关联）
    └─ 超导应用 → B11（拓扑超导：BdG Wilson loop 计算 Chern/Z₂）
                → F5（Majorana 零模：Class D Chern ≠ 0 ← BdG Wilson loop）
                → F4（Kitaev chain：1D BdG Wilson loop = Pfaffian Z₂）
```

---

**文档版本：** v1.0 (2026-04-29)
**作者（整理）：** 瓦力（Wall-E）超导 MECE 知识库
**字节大小估计：** ~12 KB

**反幻觉审计：**
- ✅ Berry 1984 [Proc. R. Soc. A 392, 45] 标注 [确定]（F10 唯一确定来源）
- ✅ Wilson 1974 / Zak 1989 / King-Smith-Vanderbilt 1993 / Yu et al. 2011 全部标注 [来源待验证]
- ✅ Z₂Pack / WannierTools 软件引用全部标注 [来源待验证]
- ✅ 数值精度数字（10⁻⁶、K=50 足够等）标注 [来源待验证]
- ✅ 路径有序的非阿贝尔性质有完整说明（反谄媚 F10.3）
- ✅ 相位追踪问题有完整说明（反谄媚 F10.4）
- ✅ Zak 相量子化的对称性条件有完整说明（反谄媚 F10.5）
- ✅ Wilson loop ≠ Berry 相的多带区别明确说明（反谄媚 F10.2）
- ✅ 规范依赖性完整说明（反谄媚 F10.1 + 1.2 节）
- ✅ 与 F1/F2/F3/B11/F4/F5 的区分关系清晰，无内容重复
- ✅ 数学公式全部提供 LaTeX + ASCII 双格式

**🎉 F 部分完成！F1-F10 全部 10 章节覆盖完毕！量子几何模块 100%！**
