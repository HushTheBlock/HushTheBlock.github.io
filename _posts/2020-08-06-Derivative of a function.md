---
layout:     post
title:      Derivative of the Frobenius norm of a matrix involving the Hadamard products
subtitle:   derivation
date:       2020-08-06
author:     Kwan
header-img: img/post-bg-coffee.jpg
catalog: 	  true
tags:
    - 学习资料
---

### Calculate $\frac{\partial\left\|\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\right\|_ {F}^{2}}{\partial \mathbf{U}}$ and $\frac{\partial\left\|\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\right\|_ {F}^{2}}{\partial \mathbf{V}}$.

We here replace the trace with the double-dot (aka Frobenius) product $\operatorname{Tr}(\mathbf{A}^{\top}\mathbf{B})=\mathbf{A}:\mathbf{B}$. Before we illustrate the process of derivation, we first provide some useful properties of double-dot product.

#### Property 1. 
$\mathbf{B}:\mathbf{D}\mathbf{E}=\mathbf{B}\mathbf{E}^{\top}:\mathbf{D}=\mathbf{D}^{\top}\mathbf{B}:\mathbf{E}$.

#### Proof:

According to the definition, $\mathbf{B}:\mathbf{D}\mathbf{E}=\operatorname{Tr}(\mathbf{B}^{\top}\mathbf{D}\mathbf{E})$, and $\mathbf{B}\mathbf{E}^{\top}:\mathbf{D}=\operatorname{Tr}(\mathbf{E}\mathbf{B}^{\top}\mathbf{D})$, $\mathbf{D}^{\top}\mathbf{B}:\mathbf{E}=\operatorname{Tr}(\mathbf{B}^{\top}\mathbf{D}\mathbf{E})$. According to the commutativity of trace operator, the above equality is easy to prove. $\square$

#### Property 2.

The double-dot product has commutativity. The proof is omited here.

Let $\mathbf{M}=\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)$, we could obtain:
$$
\partial\left\|\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\right\|_ {F}^{2}=\partial \mathbf{M}:\mathbf{M}=2\mathbf{M}:d\mathbf{M},
$$

then, we plug $\mathbf{M}=\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)$ into the above and acquire:

$$
\begin{aligned}
\partial\left\|\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\right\|_ {F}^{2}&=2\mathbf{M}:\mathbf{W}\circ d\left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\\&=2(\mathbf{W}\circ \mathbf{M}):-d\left(\mathbf{U}^{\top} \mathbf{V}\right)\\&=-2(\mathbf{W}\circ \mathbf{M}):\left(d\mathbf{U}^{\top} \cdot \mathbf{V} + \mathbf{U}^{\top}\cdot d\mathbf{V}\right)\\&=-2(\mathbf{W}\circ \mathbf{M})\mathbf{V}^{\top}:d\mathbf{U}^{\top} +(-2)\mathbf{U}(\mathbf{W}\circ \mathbf{M}): d\mathbf{V}\\&=-2\mathbf{V}(\mathbf{W}\circ \mathbf{M})^{\top}:d\mathbf{U}-2\mathbf{U}(\mathbf{W}\circ \mathbf{M}): d\mathbf{V}.
\end{aligned}
$$

Up to now, we've gained the total derivative of $\left\|\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\right\|_ {F}^{2}$, and it is easy to get partial derivatives as follows:

$$
\frac{\partial\left\|\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\right\|_ {F}^{2}}{\partial \mathbf{U}}=-2\mathbf{V}(\mathbf{W}\circ \mathbf{M})^{\top}=-2\mathbf{V}\left(\mathbf{W}\circ\mathbf{W}\circ\mathbf{R}\right)^{\top}+2\mathbf{V}(\mathbf{W}\circ\mathbf{W}\circ\mathbf{U}^{\top}\mathbf{V})^{\top},
$$

$$
\frac{\partial\left\|\mathbf{W} \circ \left(\mathbf{R}-\mathbf{U}^{\top} \mathbf{V}\right)\right\|_ {F}^{2}}{\partial \mathbf{V}}=-2\mathbf{U}(\mathbf{W}\circ \mathbf{M})=-2\mathbf{U}\left(\mathbf{W}\circ\mathbf{W}\circ\mathbf{R}\right)+2\mathbf{U}(\mathbf{W}\circ\mathbf{W}\circ\mathbf{U}^{\top}\mathbf{V}).
$$

