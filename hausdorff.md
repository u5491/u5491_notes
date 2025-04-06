---
layout: post
title: Hausdorff空間
mathjax: true
---
<blockquote class="definition">
<div class="title">Definition: Hausdorff空間</div>
<p>
$(S, \mathcal{O})$を位相空間とする. 次をみたすとき, $S$はHausdorff空間であるという : 
$$
\forall x, y \in S\ (x \neq y), \exists U \in \mathcal{N}(x), V \in \mathcal{N}(y)\ 
\mathrm{s.t.}\ U \cap V \neq \varnothing
$$
</p>
</blockquote>

### 例
- $\mathbb{R}^n$(Euclid位相)はHausdorff空間である. 
- より一般に, 距離空間$(S, d)$はHausdorff空間である. 
- Zariski位相は必ずしもHausdorff空間でない. 

<blockquote class="definition">
<div class="title">Remark : 一点集合</div>
<p>
Hausdorff空間$(S, \mathcal{O})$において, 一点集合$\lbrace x\rbrace$は閉集合である. 
</p>
</blockquote>

**証明 :** $x$と異なる任意の点$y \in S$をとる. Hausdorff性より, ある$U_y \in \mathcal{N}(x), V_y \in \mathcal{N}(y)$がとれて, $U_y \cap V_y = \varnothing$をみたす. $V_y \subset S \backslash \lbrace x\rbrace$であり

$$
\bigcup_{y \in S\backslash\lbrace x\rbrace} V_y
= S\backslash\lbrace x\rbrace
$$

より, $S\backslash\lbrace x\rbrace$は開集合である. したがって, $\lbrace x\rbrace$は閉集合である. $\square$

**注意!** : 授業で教えてもらった証明がなんかうまくいかなかったので, 上の証明はインターネットで拾ったものを参考に書きました. 

<blockquote class="definition">
<div class="title">Note : Zariski位相はHausdorff空間でないことがある</div>
<p>
$n = 1, K = \mathbb{C}$の場合を考える. $\mathbb{C}[X]$は単項イデアル整域であるので, 非自明なイデアル$I$は$f(X) \in \mathbb{C}[X]$により生成されるが, このとき$V(I)$は$f(X)$の根の集合となる. ここで, $\deg f < \infty$より$V(I)$はつねに有限集合となる. 逆に, 任意の$\mathbb{C}$の有限集合について, その元を根としてもつような$\mathbb{C}[X]$の元を構成できるため, Zariski位相における閉集合系は$\mathbb{C}$の有限集合全体からなる集合に一致する. 開集合は有限集合の補集合として定義されたため, 任意の空でない開集合は必ず交わる. 
</p>
</blockquote>
なお, 有限体$K$上のZariski位相は離散位相となるので, Hausdorff空間となる. 

<blockquote class="definition">
<div class="title">Property : コンパクトならば閉集合</div>
<p>
$(S, \mathcal{O})$をHausdorff空間とする. $F \subset S$がコンパクトならば, $F$は閉集合となる. 
</p>
</blockquote>

**証明 :** $O = S \backslash F$とする. まず, はじめに次を示す : 

$$
\begin{align}
\forall x \in O, \exists W_x \in \mathcal{N}(x)\ \mathrm{s.t.}\ W_x \subset O
\end{align}
$$

$x \in O$を固定し, $y \in F$を任意にとる. $S$はHausdorff空間なので, 次が成り立つ : 

$$
\begin{align}
\exists U_x \in \mathcal{N}(x)\cap\mathcal{O}, V_y \in \mathcal{N}(y) \cap \mathcal{O}\ \mathrm{s.t.}\ U_y \cap V_y = \varnothing
\end{align}
$$

このとき$\lbrace V_y \mid y \in F\rbrace$は$F$の開被覆であり, $F$のコンパクト性より次が成り立つ : 

$$
\exists J \subset F\ \mathrm{s.t.}\ |J| < \infty, F \subset \bigcup_{y \in J} V_y
$$

ここで, $W_x = \bigcup_{y \in J} U_y$とすると, **$J$の有限性より**$W_x$は開集合となり, $W_x \in \mathcal{N}(x) \cap \mathcal{O}$となる. 次に, $W_x \cap F = \varnothing$を示す. これは, $z \in F$について$y \in J$が存在して$z \in V_y$となるが, このとき$z \notin U_y$より$z \notin W_x$となることから従う. これより$W_x \subset O$であり, さらに

$$
O = \bigcup_{x \in O} W_x
$$

となることより$O$は開集合であり, したがって$F$は閉集合となる. $\square$

<blockquote class="definition">
<div class="title">Property : Euclid位相</div>
<p>
Euclid位相$\mathbb{R}^n$において, $X \subset \mathbb{R}^n$がコンパクトであることと, $X$が有界閉集合であることとは同値である. 
</p>
</blockquote>

**証明 :** ($\Leftarrow$) $\mathbb{R}^n$はHausdorff空間であるので, コンパクト集合$X$は閉集合である. 有界性について, $x_0 \in \mathbb{R}^n$を固定すると, $\lbrace B(x_0, \rho) \mid \rho > 0\rbrace$は$X$の開被覆となるが, $X$がコンパクトならば

$$
\exists\rho_1, \cdots, \rho_k > 0\ \mathrm{s.t.}\ X = \bigcup_{j = 1}^k B(x_0, \rho_j)
$$

このとき, $\rho = \max\lbrace \rho_1, \cdots, \rho_k\rbrace$に対し, $X \subset B(x_0, \rho)$となるので, $X$は有界となる.  
($\Rightarrow$) $X$が有界閉集合であるとき

$$
\exists L = [a_1, b_1] \times \cdots \times [a_n, b_n]\ \mathrm{s.t.}\ X \subset L
$$

となる. このとき, $L$はコンパクトである. 実際, $\mathbb{R}$におけるHeine-Borelの定理より, 各$[a_i, b_i]$はコンパクトであり, Tychonoffの定理より$L$のコンパクト性が従う. $X$は閉集合なので, $X$の任意の開被覆について, $X$の補集合とそれらとの重なりを考えたとき, これは$L$の開被覆となり, これより$X$のコンパクト性が示される. $\square$

<blockquote class="definition">
<div class="title">Corollary : コンパクト集合上の連続関数</div>
<p>
位相空間$(S, \mathcal{O})$がコンパクトであるとする. $f : S \to \mathbb{R}$が連続であるとき, $f$は最大値, 最小値をとる. 
</p>
</blockquote>

**証明 :** $R = f(S)$はコンパクトであるので, 先ほど示したことより$R$は有界閉集合となる. $R$の有界性より$\sup R, \inf R$が存在し, $R$が閉集合であることからこれらに収束する$R$の部分列をとることができるので, これらは$R$の元である. よって示された. $\square$ 