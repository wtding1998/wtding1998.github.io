+++
title = "Projection onto Stiefel manifold"
author = ["Wentao Ding"]
lastmod = 2023-08-09T15:21:11+08:00
tags = ["Optimization", "Stiefel", "Manifold"]
categories = ["Note"]
draft = false
+++

In this post, we will give some explicit formulas of the projection of a matrix \\( Y \in \mathbb{R}^{n \times p} \\) onto Stiefel manifold \\( \St(p, n) \\). Moreover, the Lipschitz continuity of the projection will be discussed.

<!--more-->


## Projection of a full column rank matrix {#projection-of-a-full-column-rank-matrix}

We firstly consider the case when \\( Y \\) is of full column rank. We will show the projection of \\( Y \\) is \\( Y(Y^{\top}Y)^{-1/2} \\).

Consider the optimization problem over the given Stiefel manifold
\\[
\min \\| X - Y \\|^2, \mbox{ s.t. } X^{\top}X = I\_{p}.
\\]
Let \\( X\_{\*} \\) be the projection of \\( Y \\). Then \\( X\_{\*} \\) is the global solution of this problem. So it satisfies [First Optimality Condition over Stiefel Manifold]({{< ref "equivalent_first_order_optimality_condition_over_stiefel_manifold.md" >}}):
\\( \nabla f(X\_{\*}) - X\_{\*} \nabla f(X\_\*)^{\top}X\_{\*} = 0 \\).
Note that \\( \nabla f(X\_{\*}) = X\_{\*} - Y \\). We have
\\[
0 = \nabla f(X\_{\*}) - X\_{\*} \nabla f(X\_{\*})^{\top}X\_{\*} = X\_{\*} - Y - X\_{\*} (X\_{\*}^{\top} - Y^{\top})X\_{\*} = X\_{\*} - Y - X\_{\*} + X\_{\*}Y^{\top}X\_{\*},
\\]
which implies

\begin{equation}\label{eq-projection-rankp-relation-X-Y}
 Y = X\_{\*}Y^{\top}X\_{\*}.
\end{equation}

Multiplying \\( Y^{\top} \\) on both sides, we have

\begin{equation}\label{eq-2}
 Y^{\top}Y = Y^{\top}X\_{\*} Y^{\top}X\_{\*} = (Y^{\top}X\_{\*})^2.
\end{equation}

Multiplying \\( X\_{\*}^{\top} \\) on both sides, we see that
\\[
X\_{\*}^{\top}Y = X\_{\*}^{\top}X\_{\*}Y^{\top}X\_{\*} = Y^{\top}X\_{\*}.
\\]
It follows that \\( Y^{\top}X\_{\*} \\) is symmetric.
Thus, \\( Y^{\top}X\_{\*} = (Y^{\top}Y)^{1/2} \\) by \eqref{eq-2}.
Now we plug it into \eqref{eq-projection-rankp-relation-X-Y} to obtain
\\[
Y = X\_{\*} (Y^{\top}X\_{\*}) = X\_{\*} (Y^{\top}Y)^{1/2}.
\\]
Thus, \\( X\_{\*} = Y(Y^{\top}Y)^{-1/2} \\). The proof is complete.


## Projection by SVD {#projection-by-svd}

Let \\( Y = U\Lambda V^{\top} \\) be the SVD decomposition of \\( Y \\), where \\( U \in \mathbb{R}^{n \times p} \\) and \\(\Lambda, V \in \mathbb{R}^{p \times p}\\). Then \\( UV^{\top} \\) is the projection of \\( Y \\) onto  the Stiefel manifold. The proof is as follows. For any \\( X \\) in Stiefel manifold,
\\[
\langle Y, X \rangle= \langle U\Lambda V^{\top}, X \rangle = \langle \Lambda, U^{\top}XV \rangle.
\\]
Note that \\(\Lambda\\) is diagonal with non-negative diagonal elememnts and \\( U^{\top}XV \\) is in Stiefel manifold. We have \\[
\langle \Lambda, U^{\top}XV \rangle \leq \sum\_{i=1}^n (\Lambda\_{i,i}),
\\]
where the equality holds when \\( U^{\top}XV = I\_p \\). Thus,
\\[
\\| Y - X \\|^2 = \\| Y \\|^2 + \\| X \\|^2 - 2 \langle Y, X \rangle \geq \\| Y \\|^2 + p - 2 \sum\_{i=1}^p \Lambda\_{i,i},
\\]
where the equality holds when \\( X = UV^{\top} \\).


## Projection by polar decomposition {#projection-by-polar-decomposition}

Finally, we show that \\( U \\) is the projection of \\( Y \\) if the polar decomposition of \\( Y \\) is \\( Y = UP \\), where \\( P \in \mathbb{R}^{p \times p} \\) is positive semi-definite.
It is sufficient to show for any other matrix \\( V \\) in the Stiefel manifold, we have
\\[
\\| UP - U \\|^2 \ge \\| UP - V \\|^2,
\\]
which is equivalent to
\\[
\langle U - V, UP \rangle \geq 0.
\\]
Actually, we can show that
\\[
\langle U - V, UP \rangle \geq \frac{1}{2} \sigma\_{\min}(P) \\| U - V \\|^2.
\\]
Let \\( P = Q^{\top}\Lambda Q \\) be the spectral decomposition of \\( P \\), where \\(\Lambda = \operatorname{\lambda\_1 , \ldots , \lambda\_p}\\). Then
\\[
\langle U - V, UP \rangle = \langle U - V, UQ^{\top} \Lambda Q \rangle = \langle UQ^{\top} - VQ^{\top}, UQ^{\top} \Lambda \rangle.
\\]
Suppose \\( UQ^{\top} = [u\_1 , \ldots , u\_p] \\) and \\( VQ^{\top} = [v\_1 , \ldots , v\_p] \\). It follows that
\\[
\langle UQ^{\top} - VQ^{\top}, UQ^{\top}\Lambda \rangle = \sum\_{i=1}^p \langle \lambda\_i(u\_i - v\_i), u\_i \rangle \geq \min\_k \lambda\_k \frac{1}{2}(\sum\_{i=1}^p   \\| u\_i - v\_i \\|^2 ),
\\]
where the last inequality follows from \\(\\| u\_i \\| = \\| v\_i \\| = 1, i=1 , \ldots , p\\).

Moreover, from the inequality we can see that the projection and polar decomposition of \\( Y \\) are unique if \\( Y \\) is of full column rank since \\(\sigma\_{\min}(P) > 0\\) in this case.

Also, it can be proved that the polar factor \\( U \\) is the projection of \\( Y \\) under any unitarily invariant norm. Check [orthogonality - Projection onto the Stiefel manifold and the orthogonal Procr...](https://math.stackexchange.com/questions/4492668/projection-onto-the-stiefel-manifold-and-the-orthogonal-procrustes-problem) for discussions about it.


## Lipschitz continuity of projection {#lipschitz-continuity-of-projection}


### No global Lipschitz constant {#no-global-lipschitz-constant}

The projection onto Stiefel manifold has no global Lipschitz constant. For example, consider two points \\( x = \epsilon, y = -\epsilon \\) where \\( \epsilon > 0 \\). Denote the projection map onto Stiefel manifold by \\(\pi\\). then \\(\pi(x) = 1\\) and \\(\pi(y) = -1\\). If there exists a constant \\( L > 0 \\) such that
\\[ \\| \pi(x) - \pi(y) \\| \leq L \\| x - y \\|,  \\]
then \\( L \geq 1 / \epsilon \\). Since \\(\epsilon\\) can be arbitrarily close to \\( 0 \\), such constant \\( L \\) does not exist.


### Local Lipschitz constant {#local-lipschitz-constant}

Fortunately, Lipschitz continuity can be established by assuming the singular values of points have a positive lower bound. Let \\( \\| \cdot \\| \\) denote an unitary invariant norm. Especially, it can be Frobenius norm or spectral norm.


#### Square case {#square-case}

When \\( n = p \\), for any two nonsingualr matrices \\( A, B \\), we have
\\[ \\| \pi(A) - \pi(B) \\| \leq \frac{2}{\sigma\_{\min}(A) + \sigma\_{\min}(B)}\\| A - B \\|. \\]
See Theorem VII.5.1 in (<a href="#citeproc_bib_item_1">Bhatia 1997</a>) and Theorem 1 in (<a href="#citeproc_bib_item_2">Li 1995</a>) for more details.


#### Non-square case {#non-square-case}

When \\( n > p \\), there are multiple bounds; see Theorem 2 and Remark 4 in (<a href="#citeproc_bib_item_2">Li 1995</a>). Here we list some of them here.

-   \\( \frac{2}{\sigma\_{\min}(A) + \sigma\_{\min}(B)} + \frac{1}{\max\\{ \sigma\_{\min}(A), \sigma\_{\min}(B) \\}} \\). In particular, this means there exists a uniform Lipschitz constant when \\(\max\\{ \sigma\_{\min}(A), \sigma\_{\min}(B) \\}\\) has a positive lower bound.
-   \\( \sqrt{(\frac{2}{\sigma\_{\min}(A) + \sigma\_{\min}(B)})^2 + (\frac{1}{\max\\{ \sigma\_{\min}(A), \sigma\_{\min}(B) \\}})^2} \\) when \\( \\| \cdot \\| \\) denotes Frobenius norm.
-   \\( \frac{1}{\min\\{ \sigma\_{\min}(A), \sigma\_{min}(B) \\}} \\).

## References

<style>.csl-entry{text-indent: -1.5em; margin-left: 1.5em;}</style><div class="csl-bib-body">
  <div class="csl-entry"><a id="citeproc_bib_item_1"></a>Bhatia, Rajendra. 1997. <i>Matrix Analysis</i>. Vol. 169. Graduate Texts in Mathematics. New York, NY: Springer New York. <a href="https://doi.org/10.1007/978-1-4612-0653-8">https://doi.org/10.1007/978-1-4612-0653-8</a>.</div>
  <div class="csl-entry"><a id="citeproc_bib_item_2"></a>Li, Ren-Cang. 1995. “New Perturbation Bounds for the Unitary Polar Factor.” <i>Siam Journal on Matrix Analysis and Applications</i> 16 (1): 327–32.</div>
</div>
