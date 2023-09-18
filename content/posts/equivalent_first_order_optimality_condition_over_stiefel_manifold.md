+++
title = "Equivalent first order optimality conditions over Stiefel manifold"
author = ["Wentao Ding"]
lastmod = 2023-09-18T20:34:01+08:00
tags = ["Optimization", "Stiefel", "Manifold"]
categories = ["Note"]
draft = false
+++

This post is a short summary of equivalent first order optimality conditions collected from several papers for the smooth optimization problem over Stiefel manifold.
Throughout this post, we consider the optimization problem \\( \min f(X) \\), s.t. \\( X \in \mathbf{St}(n,r) \\), where \\( X \in \mathbb{R}^{n \times r} \\) and \\( f \\) is smooth. Let \\( \nabla f(X) \\) be the Euclidean gradient of \\( f \\) at \\( X \\). The following statements are equivalent:

1.  \\( X \\) is a first-order stationary point of the problem.
2.  \\( \operatorname{grad} f(X) \triangleq \nabla f(X) - \frac{X}{2} (X^{\top}\nabla f(X) + \nabla f(X)^{\top}X) = 0 \\) (by definition).
3.  \\( (I - XX^{\top}) \nabla f(X) = 0 \\) and \\( X^{\top} \nabla f(X) = \nabla f(X)^{\top}X \\) (<a href="#citeproc_bib_item_1">Gao et al. 2018</a>).
4.  \\( \nabla f(X) - X \nabla f(X)^{\top}X = 0 \\) (<a href="#citeproc_bib_item_3">Wen and Yin 2013</a>; <a href="#citeproc_bib_item_1">Gao et al. 2018</a>).
5.  \\(  \nabla f(X) X^{\top} = X \nabla f(X)^{\top} \\) (<a href="#citeproc_bib_item_3">Wen and Yin 2013</a>).
6.  \\(\nabla f(X) - X(2\rho \nabla f(X)^{\top} X + (1-2\rho) X^{\top}G ) = 0\\), where \\(\rho > 0\\) is a constant (<a href="#citeproc_bib_item_2">Jiang and Dai 2015</a>).

Note that the above conditions implies that \\( \nabla f(X)^{\top}X = X^{\top} \nabla f(X) \\), that is, it is a necessary condition. When \\( n = r \\) (the feasible region is an orthogonal group), this condition becomes an equivalent condition.

## References

<style>.csl-entry{text-indent: -1.5em; margin-left: 1.5em;}</style><div class="csl-bib-body">
  <div class="csl-entry"><a id="citeproc_bib_item_1"></a>Gao, Bin, Xin Liu, Xiaojun Chen, and Ya-xiang Yuan. 2018. “A New First-Order Algorithmic Framework for Optimization Problems with Orthogonality Constraints.” <i>Siam Journal on Optimization</i> 28 (1): 302–32. <a href="https://doi.org/10.1137/16M1098759">https://doi.org/10.1137/16M1098759</a>.</div>
  <div class="csl-entry"><a id="citeproc_bib_item_2"></a>Jiang, Bo, and Yu-Hong Dai. 2015. “A Framework of Constraint Preserving Update Schemes for Optimization on Stiefel Manifold.” <i>Mathematical Programming</i> 153 (2): 535–75. <a href="https://doi.org/10.1007/s10107-014-0816-7">https://doi.org/10.1007/s10107-014-0816-7</a>.</div>
  <div class="csl-entry"><a id="citeproc_bib_item_3"></a>Wen, Zaiwen, and Wotao Yin. 2013. “A Feasible Method for Optimization with Orthogonality Constraints.” <i>Mathematical Programming</i> 142 (1-2): 397–434. <a href="https://doi.org/10.1007/s10107-012-0584-1">https://doi.org/10.1007/s10107-012-0584-1</a>.</div>
</div>
