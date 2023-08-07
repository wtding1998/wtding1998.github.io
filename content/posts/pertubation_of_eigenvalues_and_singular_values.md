+++
title = "Eigenvalues and singular values of perturbed matrices"
author = ["Wentao Ding"]
publishDate = 2023-08-07
lastmod = 2023-08-07T14:04:57+08:00
tags = ["Linear Algebra"]
categories = ["Note"]
draft = false
+++

This post is about the eigenvalues and singular values of perturbed matrices.
<!--more-->


## Eigenvalues of perturbed Hermitian matrices. {#eigenvalues-of-perturbed-hermitian-matrices-dot}

It is well known that the sum of two positive definite matrices are sill positive definite. Weyl's inequality gives an estimation of the eigenvalues of their sum as follows:
Let \\( A, B, C \in \mathbb{C}^{n \times  n} \\) be Hermitian matrices with \\( A = B+C \\). Suppose that there eigenvalues are \\(a\_i\\), \\(b\_i\\), \\(c\_i\\), \\( i \in [n] \\) and are in a descent order, that is \\(a\_1 \geq a\_2 \geq \ldots \geq a\_n\\) and so on. Then
\\[ b\_{j} + c\_k \leq a\_i \leq b\_s + c\_t \quad \text{for } j+k - n \geq i \geq s+t-1.  \\]
In particular, we have that \\(b\_i + c\_n \leq a\_i \leq b\_i + c\_1\\) for \\( i \in [n] \\).


### Fails in non-Hermitian case {#fails-in-non-hermitian-case}

Weyl's inequality does not holds for non-Hermitian matrices. Consider the following example:
\\[ B = \begin{bmatrix}1 & 3\\\\ 0 & 1 \end{bmatrix}, C = \begin{bmatrix}1 & 0\\\\ 3 & 1 \end{bmatrix}.\\]
Note that the eigenvalues of \\( B \\) and \\( C \\) are all positive. If Weyl's inequality holds, then the eigenvalues of \\( B + C \\) are supposed to be positive. However, \\( \det(B + C) < 0 \\).


## Singular values of perturbed matrices. {#singular-values-of-perturbed-matrices-dot}

The following results come from Corollary 7.3.5 of (<a href="#citeproc_bib_item_1">Horn and Johnson 2012</a>).
Let \\(A, B \in \mathbb{R}^{n \times r}\\), where $ r &le; n $ . Let \\(\sigma\_1(A) \geq \cdots \geq \sigma\_r(A)\\) and \\(\sigma\_1(B) \geq \cdots \geq \sigma\_r(B)\\) be the non-increasingly ordered singular values of \\(A\\) and \\(B\\), respectively. Then

1.  \\(\left|\sigma\_i(A)-\sigma\_i(B)\right| \leq\\|A-B\\|\_{2}\\) for each \\(i=1, \ldots, q\\);
2.  \\(\sum\_{i=1}^q\left(\sigma\_i(A)-\sigma\_i(B)\right)^2 \leq\\|A-B\\|\_F^2\\).

## References

<style>.csl-entry{text-indent: -1.5em; margin-left: 1.5em;}</style><div class="csl-bib-body">
  <div class="csl-entry"><a id="citeproc_bib_item_1"></a>Horn, Roger A, and Charles R Johnson. 2012. <i>Matrix Analysis</i>. Cambridge university press.</div>
</div>
