---
layout: post
title: 線形計画問題と双対問題
mathjax: true
---

# 線形計画問題とその双対

線形計画の標準形は次のように表されます：

$$
\begin{align}
\text{maximize} \quad & \mathbf{c}^\top \mathbf{x} \\\\
\text{subject to} \quad & A\mathbf{x} \leq \mathbf{b}, \\\\
& \mathbf{x} \geq 0
\end{align}
$$

この問題に対応する双対問題（dual problem）は：

$$
\begin{align}
\text{minimize} \quad & \mathbf{b}^\top \mathbf{y} \\\\
\text{subject to} \quad & A^\top \mathbf{y} \geq \mathbf{c}, \\\\
& \mathbf{y} \geq 0
\end{align}
$$
