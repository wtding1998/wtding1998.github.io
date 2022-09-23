+++
title = "projection onto Stiefel manifold"
author = ["Wentao Ding"]
lastmod = 2022-09-19T22:58:52+08:00
tags = ["optimization"]
draft = false
+++

In this post, we give the explicit formula of the projection of \\( Y \in \mathbb{R}^{n \times p} \\) onto Stiefel manifold \\( St(n, r) \\).
<!--more-->

## Projection of a rank \\( p \\) matrix {#projection-of-a-rank-p-matrix}

The projection of \\( Y \\) is \\( Y(Y^{\top}Y)^{-1/2} \\) if \\( Y \\) has full column rank. Here is the proof. Consider the optimization problem
\\[
\min \\| X - Y \\|^2, \mbox{ s.t. } X^{\top}X = I\_{p}.
\\]
Let \\( X\_{\*} \\) be the projection of \\( Y \\). Then \\( X\_{\*} \\) satisfies the optimality condition.
Note that \\( \nabla f(X\_{\*}) = X\_{\*} - Y \\), we have
\\[
0 = \nabla f(X\_{\*}) - X\_{\*} \nabla f(X\_{\*})^{\top}X\_{\*} = X\_{\*} - Y - X\_{\*} (X\_{\*}^{\top} - Y^{\top})X\_{\*} = X\_{\*} - Y - X\_{\*} + X\_{\*}Y^{\top}X\_{\*},
\\]
which implies

\begin{equation}\label{eq-projection-rankp-relation-X-Y}
 Y = X\_{\*}Y^{\top}X\_{\*}.
\end{equation}

Multiplying \\( Y^{\top} \\) on the left on both sides, we have
\\[ Y^{\top}Y = Y^{\top}X\_{\*} Y^{\top}X\_{\*} = (Y^{\top}X\_{\*})^2 \\]
Moreover, \\( Y^{\top}X\_{\*} \\) is symmetric, so \\( Y^{\top}X\_{\*} = (Y^{\top}Y)^{1/2} \\).
Now we plug it into \ref{eq-projection-rankp-relation-X-Y} to obtain
\\[
Y = X\_{\*} (Y^{\top}X\_{\*}) = X\_{\*} (Y^{\top}Y)^{1/2}.
\\]
Thus, \\( X\_{\*} = Y(Y^{\top}Y)^{-1/2} \\).

## References

<style>.csl-entry{text-indent: -1.5em; margin-left: 1.5em;}</style><div class="csl-bib-body">
</div>
