---
title: "What is a gauge field? Part 1: Electromagnetism"
excerpt: "This is the first post in a series that tries to discover what a gauge field is. The best
place to begin is in the easiest gauge theory, namely electromagnetism."
categories:
    - gauge-fields
tags:
    - gauge-fields
mathjax: true
aside:
  toc: true
key: gauge-fields-01
---
Get this post on [pdf here](/assets/docs/pdf_posts/gauge-fields-01.pdf).

The objective of the following posts is to attempt to give an answer to
the age-old question: What is a gauge field?

That's a tall order, alright. In order to understand what gauge fields
are, I hope to construct a direct *dictionary* between classical gauge
fields as physicists know them, and the language of principal bundles
that mathematicians use. The parallel between both is striking, but I
haven't found an actual dictionary that lets you go straight from one to
the other. And well, since I'm a completionist it doesn't just suffice
to spell it out, but rather to build it nicely.

This first part does not have too many prerrequisites: only the basics
of electromagnetism. I'll try to be as self-contained as possible in the
physics part. Without further ado, let's begin.

Potentials for the electric and magnetic field {#sec:potent-electr-magn}
==============================================

In Gaussian units, the microscopic (or vacuum) Maxwell equations are


$$ \begin{aligned}
  \boldsymbol{\nabla}\times\mathbf{E}+\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t} &=  0 & \boldsymbol{\nabla}\cdot\mathbf{E} &=  4\pi\rho\\
  \boldsymbol{\nabla}\cdot\mathbf{B} &=  0  & \boldsymbol{\nabla}\times\mathbf{B}-\frac{1}{c}\frac{\partial \mathbf{E}}{\partial t} &=  \frac{4\pi}{c}\mathbf{J},\end{aligned} $$


where $\rho$ is the electric charge density and $\mathbf{J}$ is the
electric current density. Here, the fields $\mathbf{E},\mathbf{B}$, and
the current density $\mathbf{J}$ are time-dependent vector fields on
some open subset of $U\subseteq\mathbb{R}^3$,


$$ \mathbf{E},\mathbf{B},\mathbf{J}:\mathbb{R}\times U \to \mathbb{R}^3, $$


and the charge density $\rho$ is a time-dependent scalar function on
$U$,

$$ \rho:\mathbb{R}\times U\to \mathbb{R}. $$

 The objective with these
equations is to determine the electric and magnetic fields
$\mathbf{E},\mathbf{B}$, given the source functions $\mathbf{J}$ and
$\rho$ (and boundary conditions and all that so that the PDE is actually
soluble).

Now we have a *trick* to make it easier to find a solution to the
equations. The trick is to see that we can automatically satisfy the
homogeneous equations (on the left) by a clever rewriting of
$\mathbf{E}$ and $\mathbf{B}$. Indeed, the equation
$\boldsymbol{\nabla}\cdot\mathbf{B}=0$ suggests (but does not
*imply*[^1] ) that we write


$$ \mathbf{B} = \boldsymbol{\nabla}\times\mathbf{A}, $$

 for some other
vector field $\mathbf{A}$, which we call the **magnetic vector
potential**. Once we have this, the other homogeneous equation becomes


$$ \boldsymbol{\nabla}\times\mathbf{E}+\frac{1}{c}\frac{\partial }{\partial t}(\boldsymbol{\nabla}\times\mathbf{A}) = \boldsymbol{\nabla}\times\left(\mathbf{E}+\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t}\right)=0. $$


Again, this suggests (but not always implies[^2]) that we write


$$ \mathbf{E}+\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t} = -\boldsymbol{\nabla}\phi, $$


or rather


$$ \mathbf{E} = -\boldsymbol{\nabla}\phi -\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t} $$


for some function $\phi$ which we call the **electric potential** (the
negative sign is a convention[^3]). For such choices of $\mathbf{A}$ and
$\phi$, the homogeneous Maxwell equations are immediately satisfied. Of
course the choice of $\mathbf{A}$ and $\phi$ must be such that the
inhomogeneous equations are still satisfied, but this reduces the
problem from finding two vector fields $\mathbf{E}$, $\mathbf{B}$
satisfying the full Maxwell equations to finding one scalar field $\phi$
and a vector field $\mathbf{A}$ that satisfy the (admittedly ugly)
equations

$$ \begin{aligned}
  -\boldsymbol{\nabla}^2\phi - \frac{1}{c}\frac{\partial }{\partial t}(\boldsymbol{\nabla}\cdot\mathbf{A}) &= 4\pi\rho\\
  \boldsymbol{\nabla}\times(\boldsymbol{\nabla}\times\mathbf{A})  +\frac{1}{c^2}\frac{\partial ^2\mathbf{A}}{\partial t^2} + \frac{1}{c}\frac{\partial }{\partial t}(\boldsymbol{\nabla}\phi) &= \frac{4\pi}{c}\mathbf{J}.\end{aligned} $$



Of course, the choice of $\mathbf{A}$ and $\phi$ are not *unique*. Once
we have a choice of $\mathbf{A}$ and $\phi$, then for *any* smooth
scalar field $\Lambda$, we can change $\mathbf{A}$ as


$$ \mathbf{A}' = \mathbf{A} + \boldsymbol{\nabla}\Lambda, $$

 and of course
we will still obtain


$$ \boldsymbol{\nabla}\times\mathbf{A}' = \boldsymbol{\nabla}\times\mathbf{A} + \boldsymbol{\nabla}\times(\boldsymbol{\nabla}\Lambda) = \boldsymbol{\nabla}\times\mathbf{A} = \mathbf{B}. $$


Then $\mathbf{A}'=\mathbf{A}+\boldsymbol{\nabla}\Lambda$ is also another
magnetic vector potential for $\mathbf{B}$. Under this new magnetic
potential, we have for the electric field


$$ \mathbf{E} = -\boldsymbol{\nabla}\phi - \frac{1}{c}\frac{\partial \mathbf{A}}{\partial t}=-\boldsymbol{\nabla}\phi - \frac{1}{c}\frac{\partial \mathbf{A}'}{\partial t}+\frac{1}{c}\frac{\partial }{\partial t}(\boldsymbol{\nabla}\Lambda)= -\boldsymbol{\nabla}\left(\phi- \frac{1}{c}\frac{\partial \Lambda}{\partial t}\right) -\frac{1}{c}\frac{\partial \mathbf{A}'}{\partial t}, $$


and so if we define a "new" electric potential $\phi'$ as


$$ \phi' = \phi -\frac{1}{c}\frac{\partial \Lambda}{\partial t}, $$

 we
still can write


$$ \mathbf{E} = -\boldsymbol{\nabla}\phi'-\frac{1}{c}\frac{\partial \mathbf{A}'}{\partial t}. $$


This tells us that the pair $\mathbf{A}',\phi'$ is another perfectly
good choice of potentials for $\mathbf{E}$ and $\mathbf{B}$.

**In summary**, the homogeneous Maxwell equations suggest that we write
the electric and magnetic fields $\mathbf{E}$, $\mathbf{B}$ in terms of
the potentials $\mathbf{A}$ and $\phi$. Once we have done that, we can
reduce Maxwell's equations on $\mathbf{E}$ and $\mathbf{B}$ to two
(hopefully easier) equations the potentials $\mathbf{A},\phi$. Once we
have found such potentials $\mathbf{A},\phi$, we can recover the
electric and magnetic fields as

$$ \begin{aligned}
  \mathbf{B} &= \boldsymbol{\nabla}\times\mathbf{A},\\
  \mathbf{E} &=-\boldsymbol{\nabla}\phi -\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t}.\end{aligned} $$


The choice of potentials $\mathbf{A},\phi$ is *not unique*, since for
any smooth scalar field $\Lambda$, we can define new potentials
$\mathbf{A}',\phi'$ as

$$ \begin{aligned}
  \mathbf{A}' &= A + \boldsymbol{\nabla}\Lambda,\\
  \phi' &=\phi -\frac{1}{c}\frac{\partial \Lambda}{\partial t},\end{aligned} $$


and we still obtain the same $\mathbf{E}$, $\mathbf{B}$. When we change
the potentials using a function $\Lambda$ (which remember, can be *any*
smooth function), we say that we are applying a **gauge transformation**
to the fields, and we say that $\Lambda$ is a **gauge function**. Of
course, since the fields $\mathbf{E}$ and $\mathbf{B}$ do not change
under such transformations, we say that they are **gauge invariant**.
This property is also often called a *local symmetry*, since we are
applying a "transformation" that does not change the fields (that's why
it's a *symmetry*), and this transformation can be done differently at
every point in space-time (since $\Lambda$ can be *any* smooth
function). That's where the word *local* comes from.

In special-relativistic notation {#sec:spec-relat-notat}
================================

Let's go back to square one, and let's rewrite this more neatly[^4] in
the Minkowski spacetime of special relativity. The space we are working
in is $M=\mathbb{R}\times U\subseteq \mathbb{R}^4$, with global
coordinates

$$ x^0=ct,\qquad x^1=x,\qquad  x^2=y,\qquad x^3=z, $$

 where
$c$ is the speed of light in your favorite units. We also have a metric
$\eta$ given in coordinates as


$$ \eta = \mathrm{d}{x^0}\otimes\mathrm{d}{x^0} - \sum_{i=1}^3\mathrm{d}{x^i}\otimes\mathrm{d}{x^i} = \eta_{\mu\nu}\mathrm{d}x^\mu \otimes\mathrm{d}x^{\nu}. $$


Here we used Einstein's notation, and we will follow the usual
conventions of raising and lowering indices for the isomorphism
$TM\cong T^*M$ induced by the metric[^5].

Now we (rather arbitrarily) define a $2$-form $F\in \Omega^2(M)$, called
the **Faraday** or **electromagnetic tensor** whose components with
respect to these coordinates are

$$ [F_{\mu\nu}] =
  \begin{pmatrix}
    0 & \mathbf{E}^1 & \mathbf{E}^2 & \mathbf{E}^3\\
    -\mathbf{E}^1 & 0  & -\mathbf{B}^3 &  \mathbf{B}^2\\
    -\mathbf{E}^2 & \mathbf{B}^3 & 0 & -\mathbf{B}^1\\
    -\mathbf{E}^3 & -\mathbf{B}^2 & \mathbf{B}^1 & 0
  \end{pmatrix}. $$

 This definition, at the time, is quite arbitrary but
it can be shown[^6] that is it a *somewhat* natural construction that
pops up in Maxwell's equations. A note on notation: Let's think of the
bold symbols as overriding Einstein's notation. This equation should be
seen literally, component-wise, e.g. $F_{01}=\mathbf{E}^1$, and of
course the Einstein notation doesn't add up here. It doesn't matter too
much at this point[^7].

A key feature of the electromagnetic tensor is that it is a *closed*
$2$-form, that is, its de Rham differential vanishes. The computation is
a bit tedious but we'll give a few components just so that this is not
completely blind faith. Recall that the de Rham differential of a
$k$-form $\omega\in \Omega^k(M)$ is a $(k+1)$-form with components


$$ (\mathrm{d}\omega)_{\nu_1\dots\nu_k \mu}= k!(k+1)\partial_{[\mu}\omega_{\nu_1\dots\nu_k]}. $$


The bracket stands for the total antisymmetrization of the indices in
it. Applying this to the Faraday tensor, we obtain


$$ (\mathrm{d}{F})_{012}=\frac{\partial F_{12}}{\partial x^0} -\frac{\partial F_{02}}{\partial x^1} +\frac{\partial F_{01}}{\partial x^2} = -\frac{1}{c}\frac{\partial \mathbf{B}^3}{\partial t} -\frac{\partial \mathbf{E}^2}{\partial x^1}+\frac{\partial \mathbf{E}^1}{\partial x^2} = -\left(\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t} +\boldsymbol{\nabla}\times\mathbf{E}\right)^3, $$


(that is, the third component of the equation, not the equation cubed)
and similarly for the components $(\mathrm{d}{F})\_{013}$ and
$(\mathrm{d}{F})\_{023}$. For the last component,


$$ (\mathrm{d}{F})_{123}=\frac{\partial F_{23}}{\partial x^1} -\frac{\partial F_{13}}{\partial x^2} +\frac{\partial F_{12}}{\partial x^3} = -\frac{\partial \mathbf{B}^1}{\partial x^1}-\frac{\partial \mathbf{B}^2}{\partial x^2}-\frac{\partial \mathbf{B}^3}{\partial x^3} = -\boldsymbol{\nabla}\cdot\mathbf{B}. $$


If we compute the other two components we will see that the components
of $\mathrm{d}{F}$ are precisely the components of the homogeneous
Maxwell equations. Therefore, we have that


$$ \mathrm{d}{F}=0\qquad\Leftrightarrow\qquad
  \begin{aligned}
      \boldsymbol{\nabla}\times\mathbf{E}+\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t} &=  0\\
  \boldsymbol{\nabla}\cdot\mathbf{B} &=  0
  \end{aligned}. $$

 Thus, if we assume that Maxwell's equations hold,
then $F$ is a closed $2$-form, and this suggests[^8] we write


$$ F = \mathrm{d}{A} $$

 for some $1$-form $A\in \Omega^1(M)$, called the
**electromagnetic potential**. In components, this is


$$ F_{\mu\nu} = \frac{\partial A_\nu}{\partial x^\mu}-\frac{\partial A_\mu}{\partial x^\nu}, $$


where $A = A_\mu\mathrm{d}{x^\mu}$. This electromagnetic potential
corresponds to the electric and magnetic potentials $\phi,\mathbf{A}$ as


$$ A_0 = \phi \qquad A_i = -\mathbf{A}^i. $$

 The annoying sign for the
spacial indices tell us that $A$ should be more naturally thought of as
a *vector field* instead of a $1$-form. Raise that index![^9]


$$ A^0 = \phi \qquad A^i = \mathbf{A}^i $$

 Ah, much better. Indeed, we
have for $i\geq 1$,


$$ F_{0i}=\mathbf{E}^i=\frac{\partial A_i}{\partial x^0}-\frac{\partial A_0}{\partial x^i} = \left(-\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t}-\boldsymbol{\nabla}\phi \right)^i, $$


and for instance,


$$ F_{21}=\mathbf{B}^3 = \frac{\partial A_1}{\partial x^2}-\frac{\partial A_2}{\partial x^1}=\left(\boldsymbol{\nabla}\times\mathbf{A}\right)^3. $$


This tells us that the choice of a primitive $A$ for $F$ such that
$\mathrm{d}A = F$ is exactly the same as choosing potentials
$\phi,\mathbf{A}$ for the electric and magnetic fields $\mathbf{E}$,
$\mathbf{B}$ as in the previous section.

Once again, we have that the choice of electromagnetic potential is not
unique, since we can add to $A$ any closed $1$-form
$\mathrm{d}{\Lambda}$ (for a function $\Lambda\in C^{\infty}(M)$) and
still obtain the same electromagnetic tensor $F$. If
$A'=A-\mathrm{d}{\Lambda}$, then


$$ \mathrm{d}{A'}=\mathrm{d}(A-\mathrm{d}{\Lambda})=\mathrm{d}{A} +\mathrm{d}^2\Lambda = \mathrm{d}{A} =F. $$


In components, $A'$ looks like

$$ \begin{aligned}
  A'_0&=\phi'=A_0-\frac{\partial \Lambda}{\partial x^0}=\phi -\frac{1}{c}\frac{\partial \Lambda}{\partial t},\\
  A'_i&={-\mathbf{A}'}^i = A_i-\frac{\partial \Lambda}{\partial x^i}=-(\mathbf{A} +\boldsymbol{\nabla}\Lambda)^i.\end{aligned} $$


Thus we recover the same equations for a gauge transformation:


$$ A' = A - \mathrm{d}\Lambda \qquad \Leftrightarrow \qquad  \begin{aligned}
      \mathbf{A}' &= \mathbf{A} + \boldsymbol{\nabla}\Lambda,\\
  \phi' &=\phi -\frac{1}{c}\frac{\partial \Lambda}{\partial t}
  \end{aligned} $$



Again, to summarize, we can put together the electric and magnetic
fields into a $2$-form $F$, the electromagnetic tensor, which satisfies


$$ \mathrm{d}{F}=0. $$

 This equation is automatically satisfied if there
is a $1$-form $A$ such that $F=\mathrm{d}{A}$. In this case we call $A$
an electromagnetic potential for $F$. The choice of potential is not
unique, for we can add any closed $1$-form $\mathrm{d}{\Lambda}$ to $A$
and obtain the same electromagnetic tensor. The new electromagnetic
potential is, then

$$ A' = A - \mathrm{d}{\Lambda}. $$

 This is called a
**gauge transformation**, and the ability to change the potentials is
called a **gauge freedom** (or symmetry).

What about the inhomogeneous Maxwell equations? Well, that's a little
bit more tricky. Let's write all the equations again:

$$ \begin{aligned}
  \boldsymbol{\nabla}\times\mathbf{E}+\frac{1}{c}\frac{\partial \mathbf{B}}{\partial t} &=  0 & \boldsymbol{\nabla}\times\mathbf{B}-\frac{1}{c}\frac{\partial \mathbf{E}}{\partial t}  &=  \frac{4\pi}{c}\mathbf{J}\\
  \boldsymbol{\nabla}\cdot\mathbf{B} &=  0  & \boldsymbol{\nabla}\cdot\mathbf{E} &=  4\pi\rho.\end{aligned} $$


Note that in the inhomogeneous equations, the roles of $\mathbf{E}$ and
$\mathbf{B}$ seem to be reversed, except for a sneaky negative sign.
What is this inhomogeneous equation in terms of the electromagnetic
tensor $F$?

If you've already seen this then: 1. why are you even reading this post
and 2. you already know that the inhomogeneous equations, *in
components*, take the form


$$ \frac{\partial F^{\mu\nu}}{\partial x^{\mu}}=4\pi J^\nu, $$

 where $J$
is a vector field whose components are


$$ J^0 = \rho; \qquad J^i = \frac{1}{c}\mathbf{J}^i,~~\text{for }i\geq 1. $$



Okay this is good and all, but we want a coordinate-free way to write
this. Let's try to reverse-engineer the equation. We have that $F$ is a
$2$-form, and we want to relate it via some sort of "divergence" with a
*vector field*. Instead of that, we can simply convert the vector field
$J$ into a $1$-form using the metric, but still we need to take a
derivative of $F$. The problem is that the de Rham differential
$\mathrm{d}$ will annihilate $F$, and even if it didn't, it would turn
$F$ into a $3$-form. No bueno!

Instead we want to find a way to switch the roles of $\mathbf{E}$ and
$\mathbf{B}$ in the Faraday tensor, so that the resulting tensor does
not vanish when we apply the exterior differential. We would then have a
three-form, which we want to somehow relate to the current one-form.

If this sounds familiar to you, then you've probably heard of the
**Hodge dual** or Hodge star operator. Briefly, if you have a metric $g$
on a manifold $M$ then there is an isomorphism
$\star:\Omega^{k}(M)\to\Omega^{n-k}(M)$, such that for all $k$-forms
$\omega,\nu$

$$ \alpha\wedge\star\beta = g(\alpha,\beta)\mathrm{vol}, $$


where $\mathrm{vol}$ is the volume form associated to the metric and the
metric evaluated on $k$-forms is defined as


$$ g(\alpha,\beta) := \frac{1}{k!}\alpha^{\mu_1\dots\mu_k}\beta_{\mu_1\dots\mu_k}. $$


We've discussed the Hodge star in depth in a [previous
post.](https://www.homotopico.com/2019/06/10/hodge-star.html) It can be
shown that, in coordinates, the components of the Hodge star of a
$k$-form $\beta$ are



$$ (\star\beta)_{\lambda_1\dots\lambda_{n-k}}= \pm\frac{\sqrt{|\det(g)|}}{k!}\beta^{\rho_1\dots\rho_k}\epsilon_{\rho_1\dots\rho_k\lambda_1\dots\lambda_{n-k}}, $$


where $\epsilon$ is the Levi-Civita symbol. In particular, we will care
about the stars of wedges of the basis one-forms $\mathrm{d}{x}^\mu$. In
the [previous
post](https://www.homotopico.com/2019/06/10/hodge-star.html) we showed
that if $\\{e^1,\dots,e^n\\}$ is an orthonormal basis then


$$ \star(e^{\rho_1}\wedge\dots\wedge e^{\rho_k})=g^{\rho_1\rho_1}\dots g^{\rho_k\rho_k}\epsilon^{\rho_1\dots\rho_k\nu_1\dots\nu_{n-k}}e^{\nu_1}\wedge\dots\wedge e^{\nu_{n-k}}\qquad\text{(no Einstein sum)}, $$


where $\\{\nu_1\dots\nu_{n-k}\\}$ is the complement of
$\\{\rho_1,\dots,\rho_k\\}$ in $\\{0,\dots,n-1\\}$. In
our case, $k=2$ and $n=4$ and the one-forms $\mathrm{d}{x}^\mu$ are
orthonormal, so that


$$ \star(\mathrm{d}{x}^0\wedge\mathrm{d}{x}^1)=\eta^{00}\eta^{11}\epsilon^{0123}\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3 = -\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3. $$


In a similar fashion, we can show that

$$ \begin{aligned}
  \star(\mathrm{d}{x}^0\wedge\mathrm{d}{x}^2)&=\mathrm{d}{x^1}\wedge\mathrm{d}{x}^3\\
  \star(\mathrm{d}{x}^0\wedge\mathrm{d}{x}^3)&=-\mathrm{d}{x^1}\wedge\mathrm{d}{x}^2\\
  \star(\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2)&=\mathrm{d}{x^0}\wedge\mathrm{d}{x}^3\\
  \star(\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3)&=\mathrm{d}{x^0}\wedge\mathrm{d}{x}^1\\
  \star(\mathrm{d}{x}^3\wedge\mathrm{d}{x}^1)&=\mathrm{d}{x^0}\wedge\mathrm{d}{x}^2.\end{aligned} $$


Thus, if we rewrite the Faraday tensor as

$$ \begin{aligned}
  F &= \mathbf{E}^1\mathrm{d}{x}^0\wedge\mathrm{d}{x}^1+\mathbf{E}^2\mathrm{d}{x}^0\wedge\mathrm{d}{x}^2+\mathbf{E}^3\mathrm{d}{x}^0\wedge\mathrm{d}{x}^3\\
    &\phantom{=}-\mathbf{B}^1\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3-\mathbf{B}^2\mathrm{d}{x}^3\wedge\mathrm{d}{x}^1-\mathbf{B}^3\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2,\end{aligned} $$


we obtain

$$ \begin{aligned}
  \star F&=-\mathbf{E}^1\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3 +\mathbf{E}^2\mathrm{d}{x}^1\wedge\mathrm{d}{x}^3 - \mathbf{E}^3\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2\\
         &\phantom{=}-\mathbf{B}^1\mathrm{d}{x}^0\wedge\mathrm{d}{x}^1 - \mathbf{B}^2\mathrm{d}{x}^0\wedge\mathrm{d}{x}^2 - \mathbf{B}^3\mathrm{d}{x}^0\wedge\mathrm{d}{x}^3,\end{aligned} $$


which in matrix form is

$$ [(\star F)_{\mu\nu}] =
  \begin{pmatrix}
    0 & -\mathbf{B}^1 & -\mathbf{B}^2 & -\mathbf{B}^3\\
    \mathbf{B}^1 & 0  & -\mathbf{E}^3 &  \mathbf{E}^2\\
    \mathbf{B}^2 & \mathbf{E}^3 & 0 & -\mathbf{E}^1\\
    \mathbf{B}^3 & -\mathbf{E}^2 & \mathbf{E}^1 & 0
  \end{pmatrix}. $$

 Thus, we have that the roles of $\mathbf{B}$ and
$\mathbf{E}$ in $\star F$ are reversed from those in $F$, with a sneaky
negative sign. Morally, applying the $\star$ operator gives


$$ \begin{aligned}
  F &\overset{\star}{\mapsto} \star F\\
  \mathbf{B}&\mapsto \mathbf{E}\\
  \mathbf{E}&\mapsto -\mathbf{B}.\end{aligned} $$

 Now we have that
$\mathrm{d}(\star F)$ is a *three*-form, some of whose components are


$$ (\mathrm{d}\star{F})_{012}=\frac{\partial }{\partial x^0}(\star F)_{12} -\frac{\partial }{\partial x^1}(\star F)_{02} +\frac{\partial }{\partial x^2}(\star F)_{01} = -\frac{1}{c}\frac{\partial \mathbf{E}^3}{\partial t} +\frac{\partial \mathbf{B}^2}{\partial x^1}-\frac{\partial \mathbf{B}^1}{\partial x^2} = \left(-\frac{1}{c}\frac{\partial \mathbf{E}}{\partial t} +\boldsymbol{\nabla}\times\mathbf{B}\right)^3, $$


which is


$$ (\mathrm{d}\star F)_{012} = \left(-\frac{1}{c}\frac{\partial \mathbf{E}}{\partial t} +\boldsymbol{\nabla}\times\mathbf{B}\right)^3 = \frac{4\pi}{c}\mathbf{J}^3. $$


Similarly,


$$ (\mathrm{d}\star{F})_{123}=\frac{\partial }{\partial x^1}(\star F)_{23} -\frac{\partial }{\partial x^2}(\star F)_{13} +\frac{\partial }{\partial x^3}(\star F)_{12} = -\frac{\partial \mathbf{E}^1}{\partial x^1}-\frac{\partial \mathbf{E}^2}{\partial x^2}-\frac{\partial \mathbf{E}^3}{\partial x^3} = -\boldsymbol{\nabla}\cdot\mathbf{E}  = -4\pi \rho. $$


If we put it all together, we obtain

$$ \begin{aligned}
  \mathrm{d}\star F &= \left(-\frac{1}{c}\frac{\partial \mathbf{E}}{\partial t} +\boldsymbol{\nabla}\times\mathbf{B}\right)^3\mathrm{d}{x}^0\wedge\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2 + \left(-\frac{1}{c}\frac{\partial \mathbf{E}}{\partial t} +\boldsymbol{\nabla}\times\mathbf{B}\right)^1\mathrm{d}{x}^0\wedge\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3\\
             &\phantom{=} + \left(-\frac{1}{c}\frac{\partial \mathbf{E}}{\partial t} +\boldsymbol{\nabla}\times\mathbf{B}\right)^2\mathrm{d}{x}^0\wedge\mathrm{d}{x}^3\wedge\mathrm{d}{x}^1 - (\boldsymbol{\nabla}\cdot{\mathbf{E}})\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3\\
             &= \frac{4\pi}{c}\left(\mathbf{J}^3\mathrm{d}{x}^0\wedge\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2 + \mathbf{J}^2\mathrm{d}{x}^0\wedge\mathrm{d}{x}^3\wedge\mathrm{d}{x}^1 + \mathbf{J}^1\mathrm{d}{x}^0\wedge\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3\right) - 4\pi\rho\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3\end{aligned} $$



We see that on the right-hand side we have the components of the
$4$-current $J$, but as a *three*-form. If we let $j$ be the one-form
with components $J_\mu$ (i.e., with the lowered index), we have


$$ j = \rho\mathrm{d}{x}^0 - \frac{1}{c}\left(\mathbf{J}^1\mathrm{d}{x}^1 + \mathbf{J}^2\mathrm{d}{x}^2 +\mathbf{J}^3\mathrm{d}{x}^3\right), $$


so that


$$ \star j = \rho\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3-\frac{1}{c}\left(\mathbf{J}^3\mathrm{d}{x}^0\wedge\mathrm{d}{x}^1\wedge\mathrm{d}{x}^2 + \mathbf{J}^2\mathrm{d}{x}^0\wedge\mathrm{d}{x}^3\wedge\mathrm{d}{x}^1 + \mathbf{J}^1\mathrm{d}{x}^0\wedge\mathrm{d}{x}^2\wedge\mathrm{d}{x}^3\right). $$


Thus, we identify:

$$ \mathrm{d}\star F = -4\pi \star j. $$

 This can also
be written as

$$ \star\mathrm{d}\star F = 4\pi j. $$

 Finally, we obtain
the Maxwell equations written in a coordinate-free way in terms of
differential forms:

$$ \begin{aligned}
  \mathrm{d}F &=  0, & \star\mathrm{d}\star F &=4\pi j.\end{aligned} $$



These are the *field equations* of the electromagnetic field. The
homogeneous equation $\mathrm{d}{F}=0$ talks about *conservation of
charge*, and the inhomogeneous equation
$\star\mathrm{d}\star F = 4\pi j$ tells how the electromagnetic field
$F$ responds to the presence of charges and currents (represented by
$j$). The form of these equations is typical of a gauge field, as we
shall see in future posts.

Takeaway and future {#sec:takeaway-future}
===================

We saw that the inhomogeneous Maxwell equations allow (in some cases,
depending on the topology of the underlying space) us to write the
electric and magnetic fields $\mathbf{E},\mathbf{B}$ in terms of simple,
auxiliary potentials $\phi,\mathbf{A}$. The choice of these potentials
is not unique, and the fields $\mathbf{E},\mathbf{B}$ remain invariant
under certain transformations of the potentials, called *gauge
transformations*. At this point, the potentials are no more than
auxiliary mathematical objects that help us solve Maxwell's equations,
but we shall see that they can be attributed a physical interpretation
in the quantum case.

We also saw a unifying description of the electric and magnetic fields
into an electromagnetic tensor in $4D$ spacetime, and we rewrote
Maxwell's equations in a neater form that is typical of gauge fields (as
we shall see in the future).

What comes next is adding *matter* to this whole issue: introducing
objects that can interact with the electromagnetic field. We will also
see a Lagrangian description of the field equations, which again will be
typical of gauge fields.

References {#sec:references}
==========

-   Jackson, J. D. (1998). *Classical Electrodynamics, Third Edition*.
    Chapter 6, explains it *way* better than I do.

-   Báez, J. C. and Muniain, J. P. (1994). *Gauge Fields, Knots, and
    Gravity*, World Scientific. Section I.5.

-   Fecko, M. (2006). *Differential Geometry and Lie Groups for
    Physicists*. Cambridge University Press.

Thanks to Laura Arboleda for checking style and consistency <3 

[^1]: See the [previous
    post](https://www.homotopico.com/2019/06/10/hodge-star.html) on the
    Hodge star.

[^2]: See the [previous
    post](https://www.homotopico.com/2019/06/10/hodge-star.html) on the
    Hodge star.

[^3]: which does have a neat physical interpretation in terms of energy,
    but which we shall not discuss.

[^4]: For our purposes, this rewriting is simply for the sake of making
    everything clearer. What we are really doing is rewriting the
    equations of electromagnetism in the language of special relativity.
    It is no coincidence that this amounts just to a *rewriting* without
    any modifications to the equations of electromagnetism: special
    relativity was essentially *made to work* with classical
    electromagnetism. See the end of Jackson (or any decent book on
    relativity) for more details on special-relativistic
    electromagnetism.

[^5]: For more details on this check any decent book on relativity, for
    example Carroll, D'Inverno or Schutz.

[^6]: Uhh stay tuned for another post, I guess?

[^7]: This can be fixed by introducing new $4$-vectors $E,B$ with
    $E^0=0,E^i=\mathbf{E}^i$ (same for $B$), and then *lowering* the
    index and *defining* $F_{0i}:=-E_i=E^i=\mathbf{E}^i$ (and
    equivalently for $B$) but that's too much work and potentially more
    confusing.

[^8]: But does not imply! Again, this depends on $H^2(M)\cong H^2(U)$
    being trivial.

[^9]: Index gymnastics with the Minkowski metric is quite easy: In my
    convention (the one true convention, fight me) with positive time
    and negative space, the time index remains the same while the space
    indices gain a negative sign whenever they are raised or lowered (as
    can be easily checked).
