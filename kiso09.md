---
layout: default
title: "基礎数理 9 - 階数と固有値"
---

### 基礎数理 9 - 階数, 固有値

**Thm**（階数の同値な定義）  
行列 $A$ の一次独立な列（行）の最大本数として定義される階数 $\mathrm{rank}\ A$ は，$A$ の正則行列の最大次数，および $\dim \mathrm{Im}\ A$ に等しい．

上の同値な定義をうまく使うと，次が示せる：

**Thm**（階数の性質）

- $\mathrm{rank}\ AB \leq \min \lbrace \mathrm{rank}\ A, \mathrm{rank}\ B \rbrace$
- $S, T$ が正則ならば $\mathrm{rank}\ A = \mathrm{rank}\ SAT$
- $\forall A, B \in \mathbb{R}^{m \times n}, \mathrm{rank}\ (A + B) \leq \mathrm{rank}\ A + \mathrm{rank}\ B$
- （証明が $2$ 通りある） $\forall A \in \mathbb{R}^{m \times n}, B \in \mathbb{R}^{n \times p}, \mathrm{rank}\ A + \mathrm{rank}\ B - n \leq \mathrm{rank}\ AB$
- （行列形についての条件は省略） $\mathrm{rank}\ AB + \mathrm{rank}\ BC \leq \mathrm{rank}\ ABC + \mathrm{rank}\ B$

---

**Def**（対称, 正定値, 半正定値）

---

**Thm**  
正方行列 $A$ が正定値対称ならば，$\det A > 0$ が成り立つ．（逆は成り立たない）

---

**Def**（正規行列，ユニタリ行列，エルミート行列）  
$A$ を複素正方行列とする．

- $AA^* = A^*A$ が成り立つとき，$A$ は **正規行列** であるという．  
- さらに $AA^* = A^*A = I$ が成り立つとき，$A$ は **ユニタリ行列** であるという．  
- さらに $A = A^*$ が成り立つとき，$A$ は **エルミート行列** であるという．

---

**Thm**（正規行列の対角化可能性）  
複素正方行列 $A$ が正規行列であることと，$A$ が対角化可能であることとは同値．

---

**Thm**（量子力学でもよく使う）  
複素正方行列 $A$ がエルミート行列ならば，$A$ の固有値はすべて実数となる．

---

**Def**（Rayleigh 商）  
$A$ をエルミート行列とする．$A, x \neq 0$ について，Rayleigh 商 $R_A(x)$ は次式で定義される：

$$
R_A(x) := \frac{x^*Ax}{x^*x}
$$

$A$ の最大固有値，最小固有値をそれぞれ $\lambda_\mathrm{max}, \lambda_\mathrm{min}$ とおくと，Rayleigh 商について次のことが成り立つ（練習問題）：

$$
\lambda_\mathrm{max} = \max_{x \neq 0} R_A(x), \quad
\lambda_\mathrm{min} = \min_{x \neq 0} R_A(x)
$$

---

**Thm**（Courant-Fischer の定理）  
$A$ をエルミート行列とし，その固有値を $\lambda_1 \geq \cdots \geq \lambda_n$ とおくと，次が成り立つ：

$$
\lambda_k = \max_{U_k}\min\left\{R_A(x) \mid x \in U_k \setminus \left\{0\right\} \right\}
$$

ここで，$U_k$ は $k$ 次元部分空間である．

---

**Proof**  
$\lambda_1, \cdots, \lambda_n$ に対応する直交固有ベクトルをそれぞれ $u_1, \cdots, u_n$ として：

$$
\begin{align}
V_k &= \mathrm{span}\left\{u_1, \cdots, u_k\right\} \\
W_l &= \mathrm{span}\left\{u_{n - l + 1}, \cdots, u_n\right\}
\end{align}
$$

とおく．このとき，先ほどの Rayleigh 商に関する性質より：

- $\forall x \in V_k,\quad \lambda_1 \leq R_A(x) \leq \lambda_k$  
- $\forall x \in W_l,\quad \lambda_{n - l + 1} \geq R_A(x) \geq \lambda_n$

が成り立つ．さて，任意の $k$ 次元部分空間 $U_k$ について，$U_k \cap W_{n - k + 1} \neq \lbrace 0 \rbrace$ であり，これより：

$$
\min\left\{R_A(x) \mid x \in U_k,\ x \neq 0\right\} \leq \lambda_k
$$

特に $U_k = V_k$ のとき等号が成立することもわかる．これより示すべきことが言えた．$\square$
