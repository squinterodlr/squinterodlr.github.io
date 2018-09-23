---
author:
- Santiago Quintero de los Ríos
title: 'Why is momentum the generator of translations?'
excerpt: In quantum mechanics, it is often stated that <i>the momentum [operator] is the generator of translations</i>. However, most texts fail to give a satisfactory justification to this claim, if any is given at all. What we will do here is define <i>precisely</i> what it means for observable to be a generator of a group of transformations, both in quantum and classical mechanics, and prove that, indeed, the momentum observable <i>is</i> the generator of translations in classical mechanics.
categories:
    - honest physics
    - quantum mechanics
    - classical mechanics
tags:
    - quantum mechanics
    - classical mechanics
    - canonical transformation
    - infinitesimal generator
    - poisson bracket
    - symplectic geometry
mathjax: true
---

Get this post [in pdf format here](/assets/docs/pdf_posts/momentum-generator-translations.pdf).

In quantum mechanics, it is often stated that *the momentum \[operator\]
is the generator of translations*. However, most texts fail to give a
satisfactory justification to this claim, if any is given at all. In
some cases, the proof is simply begging the question. In others, the
burden of proof is shifted to classical mechanics, stating that “this
was already proved in classical mechanics”. Again, most standard texts
of classical mechanics fail to give a clear proof of this claim,
although the mathematical apparatus is there. What we will do here is
define *precisely* what it means for observable to be a generator of a
group of transformations, both in quantum and classical mechanics, and
prove that, indeed, the momentum observable *is* the generator of
translations in classical mechanics.

The origin of the question
--------------------------

We define the translation operator $\hat{T}_a$ acting on elements
$\psi\in L^2(\mathbb{R})$ (the Hilbert space of square-integrable
complex functions over $\mathbb{R}$) by, of course, translating the
wavefunction a distance $a$ to the right:
\begin{equation}(\hat{T}_a\psi)(x) := \psi(x-a).\end{equation}
This operator is actually a whole
family of operators that depend on the parameter $a$. It is clear that
$\hat{T}_0$ is the identity operator. Now since this family of operators
is particularly well-behaved[^1], it has an **infinitesimal generator**,
which is some operator $\hat{w}$ such that
\begin{equation}\label{eq:1} \hat{T}_a = \exp\left(-ia\hat{w}\right).\end{equation}

Yes, I know that the
standard name for this generator is $\hat{p}$, but I am trying to remove
any possible meaning to this operator. For the time being, we only know
that $\hat{w}$ is the generator of translations. That’s why I don’t call
it $\hat{p}$.

What does $\hat{w}$ look like? One way to calculate the infinitesimal
generator of a family of operators is by evaluating the derivative at
$a=0$. If we expand the right-hand side of equation \[eq:1\] as a power
series, then

$$\label{eq:3}
\exp\left(-ia\hat{w}\right) = \sum_{n=0}^{\infty}\frac{1}{n!}(-ia\hat{w})^n,$$

then it follows that

\begin{equation}\label{eq:4}
\left.\frac{\mathrm{d}}{\mathrm{d}a}\right\vert\_{a = 0}\hat{T}_a = \left.\frac{\mathrm{d}}{\mathrm{d}a}\right\vert\_{a = 0} \exp\left(-ia\hat{w}\right) = -i\hat{w}.\end{equation}
  
So let $\psi$ be any function on $L^2(\mathbb{R})$. We have that

$$\left.\frac{\mathrm{d}}{\mathrm{d}a}\right\vert_{a = 0}\hat{T}_a\psi(x) = \left.\frac{\mathrm{d}}{\mathrm{d}a}\right\vert_{a = 0}\psi(x-a) = -\frac{\mathrm{d}}{\mathrm{d}x}\psi(x),$$

so we can say that the infinitesimal generator is

\begin{equation}\label{eq:5}
\hat{w} = -i{\frac{\mathrm{d}}{\mathrm{d}x}}.\end{equation}

And hey, look at
that. It turns out that this is what we call the momentum operator in
quantum mechanics.

However, it is not clear **at all** why the operator
$-i{\frac{\mathrm{d}}{\mathrm{d}x}}$ should be given the highly
suggestive name of “momentum”. So this it’s not that the generator of
translations is momentum because it has the form
$-i{\frac{\mathrm{d}}{\mathrm{d}x}}$, but the other way around:

We say that $-i{\frac{\mathrm{d}}{\mathrm{d}x}}$ is the momentum
operator, because it is the one that generates translations.

Therefore, the question is shifted: **Why do we give the name “momentum”
to the operator that generates translations?**

The usual answers 
-----------------

If you only want a half-plausible argument, here it goes. Let $\hat{x}$
be the position operator, that is the expectation value
${\left\langle \psi \middle\vert \hat{x}\psi\right\rangle}$ is the
expected value for the position of a particle in state $\psi$. It can be
shown that the position operator acts on wavefunctions by multiplication
by the variable $x$, i.e. $$(\hat{x}\psi)(x)=x\psi(x).$$ This equation
can also be used to define $\hat{x}$. Now we want to compute the
commutator ${\left[\hat{x},\hat{w}\right]}$. On one hand, we have:

$$(\hat{x}\hat{w}\psi)(x) = -ix \frac{\mathrm{d}}{\mathrm{d}x}\psi(x),$$

but on the other hand,

$$(\hat{w}\hat{x}\psi)(x) = -i\frac{\mathrm{d}}{\mathrm{d}x}\left(x\psi(x)\right) = -i\left(\psi(x) + x\frac{\mathrm{d}}{\mathrm{d}x}\psi(x)\right).$$

Then, clearly

$${\left[\hat{x},\hat{w}\right]}\psi(x) = i\psi(x),$$

and so $\left[\hat{x},\hat{w}\right]=i\hat{I}$. Now we consider the
“quantization rule” that turns *classical* observables $f$ into
Hermitian operators $\hat{f}$ and that turns Poisson brackets *almost*
into Lie brackets

$$\left\{f,g\right\}\mapsto i\left[ \hat{f},\hat{g} \right]$$

and what we do is go backwards! We found an operator $\hat{w}$ that
satisfies the commutation relation
${\left[\hat{x},\hat{w}\right]}=i\hat{I}$, so the *classical*
observables they come from satisfy the Poisson-bracket relation
$${\left\{x,w\right\}}=1$$. We know that $\hat{x}$ is the position
operator, so $x$ must be the position observable. On the other hand, we
know that for the canonical momentum $p$,

$${\left\{x,p\right\}} = {\frac{\partial x}{\partial x}} {\frac{\partial p}{\partial p}}-{\frac{\partial x}{\partial p}} {\frac{\partial p}{\partial x}} = 1.$$

We can clearly see that $$\left\{x,p\right\}=\left\{x,w\right\}=1$$,
so this suggests that $w=p$! And we’re done. $w$ is the momentum, so the
operator $\hat{w}$ is the momentum operator.

**But wait a minute...**

The relation
$$\left\{x,w\right\} = 1$$
is not enough to *define* $w$!
This is because the operator
$$f\mapsto\left\{x,f\right\}$$ is
degenerate. As a trivial example, $$\left\{x,p+x\right\} = 1,$$ and
actually, for any function $f(x)$ that *does not depend on* $p$, it
follows that $$\left\{x,p+f(x)\right\}=1.$$ This means that $w$ is an
observable of the form $ w = p + f(x)$ for *some* function $f(x)$. At
this point you might think “eh, close enough”. And fair enough, then
you’re done!

But I’m not thoroughly (actually, not at all) satisfied. There is
another clue though. This previous argument is one of two that I’ve seen
in QM books. The other one is as follows:

*In classical mechanics it is shown that momentum is the generator of
translations.*

And well, yes, that could be enough for our purposes. We can’t expect
every new theory to work out of the box and be able to stand by itself,
right? When we construct a new theory from a mathematical perspective,
we look back to other theories that are well-established and we
understand, look for analogies and similarities, and interpret the
symbols in such a way that everything is as consistent as possible with
what came before.

Therefore it is quite reasonable to say that this operator $\hat{w}$ is
the momentum operator if we already know from classical mechanics that
the generator of translations is the momentum. We’ve shown that in
quantum mechanics, translations *also* have infinitesimal generators, so
it is natural to interpret those as momenta.

Again, that is **if** we already know from classical mechanics that
momentum is the generator of translations. And I think I missed that
lecture? That’s a big “if”.

That quote up there shifts the burden of proof to classical mechanics.
So what we’re going to do is plunge into classical mechanics and try to
show that momentum is the generator of translations from two different
points of view: the “standard” Goldstein point-of-view, and the more
modern symplectic geometry point-of-view. We will see from both that we
can reasonably show that, in a certain way, momentum is the generator of
translations.

The standard point of view
--------------------------

More precisely, what we will prove is the following:

To each (classical) observable $f$ we can *canonically* assign a
one-parameter group of *canonical* transformations $\Phi_a$ that
preserve $f$. In this case, we say that $f$ generates $\Phi_a$. When we
choose the canonical momentum $f=p$, the resulting transformations are
translations, and thus we say that $p$ is the generator of translations.

In this first section, we will do it in a bit of a dirty way. If
infinitesimals make you uncomfortable (completely understandable), then
always note that when we write, e.g. $\tilde{x} = x + \epsilon X$, what
we mean is that $\tilde{x}=\tilde{x}(\epsilon)$ is a function of
$\epsilon$, that $\tilde{x}(0)=x$, and
$X = \lim_{\epsilon\to 0}\frac{1}{\epsilon}\tilde{x}(\epsilon)$. If you
would like to see a more concise proof that requires a bit of
differential topology, skip to the next section.

Consider some system with phase space $\mathcal{S}$, with canonical
coordinates $q^i,p_j$, and let $f$ be an arbitrary observable. We want
to find a *canonical* transformation[^2] $Q^i = Q^i(q,p)$,
$P_j = P_j(q,p)$ that preserves $f$ and depends on only one parameter
$\epsilon$. For small $\epsilon$, we can write


$$\begin{aligned}
    Q^i(\epsilon) &= q^i + \epsilon A^i\\
    P_j(\epsilon) &= p_j + \epsilon B_j
  \end{aligned},$$


  with $A^i,B_j$ functions of $q,p$ that we want to
determine. Since we want these transformations to be canonical, the
Poisson brackets must be conserved, so

\begin{equation}\begin{aligned}
    {\left\{q^i,p_i\right\}} = 1 &= {\left\{Q^i,P_i\right\}} \\
    &= {\left\{q^i + \epsilon A^i,p_i + \epsilon B_i\right\}}\\
    &= {\left\{q^i,p_i\right\}} + \epsilon\left({\left\{A^i,p_i\right\}}+{\left\{q^i,B_i\right\}}\right) + \mathcal{O}(\epsilon^2).
    \end{aligned}\end{equation}

Then, working up to first order in $\epsilon$, we
require that

$${\left\{A^i,p_i\right\}}+{\left\{q^i,B_i\right\}} = 0.$$


Unravel these Poisson brackets,

$${\left\{A^i,p_i\right\}} = \sum_k\left({\frac{\partial A^i}{\partial q^k}}{\frac{\partial p_i}{\partial p_k}} - {\frac{\partial A^i}{\partial p_k}}{\frac{\partial p_i}{\partial q^k}}\right) = {\frac{\partial A^i}{\partial q^i}}$$

$${\left\{q^i,B_i\right\}} = \sum_k\left({\frac{\partial q^i}{\partial q^k}}{\frac{\partial B_i}{\partial p_k}} - {\frac{\partial q^i}{\partial p_k}}{\frac{\partial B_i}{\partial q^k}}\right) = {\frac{\partial B_i}{\partial p_i}},$$

then we require $A^i,B_i$ to be such that

\begin{equation}\label{eq:2}
{\frac{\partial A^i}{\partial q^i}} + {\frac{\partial B_i}{\partial p_i}} = 0.\end{equation}


One way to guarantee that condition is satisfied is by finding some
*other* observable, say $g$, and write

$$\begin{equation}\label{eq:7}
  \begin{aligned}
    A^i &= {\frac{\partial g}{\partial p_i}}\\
    B_j &= -{\frac{\partial g}{\partial q^j}}
    \end{aligned}.\end{equation}$$

However, not every $g$ will work, since we also
require the transformation to preserve the observable $f$. So again, for
small $\epsilon$, we can write

$$\begin{align}
    f\left(Q^i,P_j \right) &= f\left(q^i+\epsilon A^i,p_j+\epsilon B_j\right)\\
    &= f\left(q^i,p_j\right) + \epsilon\sum_k\left(A^k{\frac{\partial f}{\partial q^k}} + B_k{\frac{\partial f}{\partial p_k}}\right) + \mathcal{O}(\epsilon^2).
    \end{align}$$

Since we require the transformation to preserve $f$,
then $f\left(Q^i,P_j \right) = f(q^i,p_j)$ and thus

\begin{equation}\label{eq:6}
\sum_k\left(A^k \frac{\partial f}{\partial q^k}  + B_k \frac{\partial f}{\partial p_k} \right) = 0.\end{equation}


But again, if we assume that $A^i,B_j$ come from the partial derivatives of an observable $g$, this condition becomes

$$\sum_k \left( \frac{\partial g}{\partial p^k} \frac{\partial f}{\partial q^k}  -  \frac{\partial g}{\partial q^k} \frac{\partial f}{\partial p_k} \right) =  \left\{f,g\right\} = 0 $$


Therefore the admissible observables $g$ that can be used for equation
are such that $${\left\{f,g\right\}}=0$$. Which one is the *absolute
simplest one* to choose? Well $f$ itself! This works since
$${\left\{f,f\right\}}=0$$. Therefore the *natural* choice is $g=f$, so
that the transformation *for infinitesimal* $\epsilon$ is

$$\label{eq:8}
  \begin{aligned}
    Q^i(\epsilon) &= q^i + \epsilon {\frac{\partial f}{\partial p^i}}\\
    P_j(\epsilon) &= p_j - \epsilon {\frac{\partial f}{\partial q^j}}
  \end{aligned}.$$

This equation only holds for infinitesimally small
$\epsilon$, since we’ve been working only up to first order. What we
want now is to write the exact solution to large $\epsilon$. To do so,
note that this equation gives us a *differential equation* for $Q$ and $P$:
writing $q^i=Q^i(0), p_j=P_j(0)$, it can be easily seen that


$$\label{eq:13}
  \begin{aligned}
    {\frac{\mathrm{d}Q^i}{\mathrm{d}\epsilon}} &= {\frac{\partial f}{\partial p^i}}\\
    {\frac{\mathrm{d}P_j}{\mathrm{d}\epsilon}} &= -{\frac{\partial f}{\partial q^j}}.
  \end{aligned}$$

Note that these are just like the Hamilton-Jacobi
equations, except that “time” is $\epsilon$ and the “Hamiltonian” is
$f$!

Now we see how any general observable changes when we do an
infinitesimal transformation . Let $g$ be any observable. Then, if we
start at a point $(q_0,p_0)$, and write
$(q_1,p_1)=(Q(\epsilon),P(\epsilon))$ (I’m dropping the $i,j$ indices),
then

$$\begin{aligned}
    g\left(Q^i(\epsilon),P_j(\epsilon) \right) &= g\left(q_0^i+\epsilon \left.{\frac{\partial f}{\partial p_{j}}}\right|_{(q_0,p_0)},p_{0,j}-\left.{\frac{\partial f}{\partial q^j}}\right|_{(q_0,p_0)}\right)\\
    g(q_1,p_1)&= g\left(q_0,p_{0}\right) + \epsilon\sum_k\left(\left.{\frac{\partial f}{\partial p_{k}}}\right|_{(q_0,p_0)}\left.{\frac{\partial g}{\partial q^k}}\right|_{(q_0,p_0)} - \left.{\frac{\partial f}{\partial q^k}}\right|_{(q_0,p_0)}\left.{\frac{\partial g}{\partial p_k}}\right|_{(q_0,p_0)}\right) + \mathcal{O}(\epsilon^2)\\
    g(q_1,p_1)&= g\left(q_0,p_{0}\right) + \epsilon\left.{\left\{g,f\right\}}\right|_{(q_0,p_0)} +\mathcal{O}(\epsilon^2).
\end{aligned}$$

How do we go to large $\epsilon$? Well, the last
equation tells us that

$${\frac{\mathrm{d}}{\mathrm{d}\epsilon}}g\left(Q(\epsilon),P(\epsilon)\right) = {\left\{g,f\right\}}_{Q(\epsilon),P(\epsilon)},$$

therefore, if we write $g(\epsilon) = g(Q(\epsilon),P(\epsilon))$,
taking the derivative with respect to $\epsilon$ again we obtain:

$$\frac{\mathrm{d}^2}{\mathrm{d}\epsilon^2} g\left(\epsilon\right) = \frac{\mathrm{d}}{\mathrm{d}\epsilon} \left\{g,f\right\}_\epsilon = \left\{\left\{g,f\right\},f\right\}_\epsilon.$$

So if we call $X_f$ the differential operator
$$X_f(g):=\left\{g,f\right\}$$, we can see that

$$\frac{\mathrm{d}^n}{\mathrm{d}\epsilon^n}g\left(\epsilon\right) = X_f(X_f(\dots X_f(g)))_{\epsilon}={X_f}^n(g)_{\epsilon}.$$

And thus, by Taylor-expanding $g$ with respect to $\epsilon$ around
$\epsilon=0$, we see that

$$\label{eq:12}
  g(\epsilon) = \sum_{n=0}^{\infty}\frac{1}{n!}\left.{\frac{\mathrm{d}^n}{\mathrm{d}\epsilon^n}}\right|_{\epsilon=0}g(\epsilon) = \sum_{n=0}^{\infty}\frac{1}{n!}{X_f}^n(g)_{(q_0,p_0)} = \exp\left(\epsilon {X_f}(0)\right)g.$$
  
We call $X_f$ the **infinitesimal generator** associated to $f$.

Alright. We should stop here for a bit and gather what we have. We have
shown that for any observable $f$, we can find a family of canonical
transformations, which we write as $Q(\epsilon),P(\epsilon)$, given by
the set of Hamilton-Jacobi-like equations . Note that if we fix a
starting point $(q_0,p_0)$, this family of transformations gives rise to
a *curve* in phase space, given by $q= Q(\epsilon),p=P(\epsilon)$. Any
other observable $g$ also changes along this curve as
$g(\epsilon) = \exp(\epsilon X_f(0))g$, or rather as
$$\frac{\mathrm{d}g}{\mathrm{d}\epsilon}=\left\{g,f\right\}$$. In
particular, $f$ is constant along this curve, since
$$\frac{\mathrm{d}}{\mathrm{d}\epsilon}f = \left\{f,f\right\}=0$$.
Therefore the family of transformations is canonical and preserves $f$,
as was desired.

Now here comes what was promised. If we choose $f=p_j$, the momentum
observable, then the infinitesimal generator associated to $p_j$,
$X_{p_j}$, is the differential operator

$$X_{p_j}(g) = {\left\{g,p_j\right\}} = \sum_{k}{\frac{\partial g}{\partial q^k}}{\frac{\partial p_j}{\partial p_k}} - {\frac{\partial g}{\partial p_k}}{\frac{\partial p_j}{\partial q^k}} = {\frac{\partial }{\partial q^j}}(g).$$

Ring any bells?

Furthermore, the family of transformations is the solution to the
Hamilton-Jacobi-like equations with $f=p_j$, i.e.

$$\label{eq:14}
  \begin{aligned}
    {\frac{\mathrm{d}Q^i}{\mathrm{d}\epsilon}} &= {\frac{\partial p_j}{\partial p^i}} = \delta^i_j\\
    {\frac{\mathrm{d}P_k}{\mathrm{d}\epsilon}} &= -{\frac{\partial p_j}{\partial q^k}} = 0,
  \end{aligned}$$

which is readily integrated, given an initial point $q_0 = Q(0),p_0=P(0)$:

$$Q^j(\epsilon) = q_{0}^j + \epsilon;$$

and all
the other coordinates constant. This is indeed a translation in the
$j$-th space coordinate.

So there you have it! In classical mechanics, to each observable $f$ we
assign a differential operator $X_f$ that generates one-parameter
canonical transformations that preserve $f$. In the case where $f=p$,
the differential operator is $X_p = \frac{\partial }{\partial q}$, and
the canonical transformations are translations! Therefore we say that
**momentum is the generator of translations**.

The mathematician’s way 
-----------------------

This way is basically exactly the same as the one before, just with the
more sophisticated language of differential topology, specifically in
the context of symplectic manifolds. It can be easily seen that the
results given here are exactly the same as the results given in the
previous section, when we write them in Darboux coordinates.

So first, some definitions.

A **symplectic manifold** is a smooth manifold $\mathcal{M}$ of
dimension $2n$ endowed with a closed, non-degenerate $2$-form $\omega$,
which we call a **symplectic form**. It can be shown that for each point
$x\in \mathcal{M}$ there exists a neighborhood $U$ of $x$ and
coordinates $q^1,\dots,q^n,p_1,\dots,p_n$ such that the symplectic form
can be written as $$\label{eq:11}
  \omega = \mathrm{d}q^{\mu}\wedge\mathrm{d}p_{\mu}.$$ Here we are
using Einstein’s sum notation. This result is **Darboux’s theorem**, and
the coordinates $(q^\mu,p_\mu)$ are called **Darboux coordinates**.

Since $\omega$ is non-degenerate, it induces an isomorphism
$(-)\_\flat:T_p\mathcal{M}\to T_p^*\mathcal{M}$, given pointwise by the
relation

$$\label{eq:10}
  v_\flat(u):=\omega(v,u)$$

for all $u,v\in T_p\mathcal{M}$ and all
$p\in\mathcal{M}$. The inverse of $(-)_\flat$ is denoted by
$(-)^\sharp:T_p^*\mathcal{M}\to T_p\mathcal{M}$.

This is basically all we need! Let $f\in C^{\infty}(\mathcal{M})$. Then
we can define the **Hamiltonian vector field associated to $f$**,
denoted by $X_f\in\mathfrak{X}(\mathcal{M})$, as

$$\label{eq:15}
  X_f = (\mathrm{d}f)^{\sharp}.$$

By this definition, for any other
vector field $Y$, we have that

$$\label{eq:16}
  \omega(X_f,Y) = \mathrm{d}f(Y)= Y[f].$$

Therefore an alternative
definition for $X_f$ is the unique vector field such that
$\iota_{X_f}\omega = \mathrm{d}f$.

Using Cartan’s magic formula, we see that

$$\label{eq:17}
  L_{X_f}\omega = \iota_{X_f}(\mathrm{d}\omega) + \mathrm{d}\left(\iota_{X_f}\omega\right) = 0.$$

Here, the first term is zero since $\omega$ is closed (i.e.
$\mathrm{d}\omega=0$), and the second one is zero too since
$\iota_{X_f}\omega=\mathrm{d}f$, and $\mathrm{d}^2=0$. In addition
to this, the directional derivative of $f$ along $X_f$ is zero, since

$$\label{eq:19}
  X_f(f) = \mathrm{d}f(X_f) = \iota_{X_f}\omega(X_f)=\omega(X_f,X_f)=0.$$
  
This means that if $\Phi^f_\tau$ is the flow of $X_f$, then for all
values of $\tau$

$$\label{eq:18}
  \left(\Phi^f_{\tau}\right)^*\omega = \omega,$$

and
$f\circ\Phi^f_\tau = f$. That is, neither $f$ nor $\omega$ change along
the integral curves of the Hamiltonian vector field associated to $f$.

Furthermore, since $\Phi^f_{\tau}:\mathcal{M}\to\mathcal{M}$ is a
diffeomorphism, then it satisfies the conditions for being a
**symplectomorphism** or **canonical transformation**. Namely, a
diffeomorphism $f:\mathcal{M}\to\mathcal{N}$ between two symplectic
manifolds $(\mathcal{M},\omega)$ and $(\mathcal{N},\Omega)$ is a
symplectomorphism if $f^*\Omega=\omega$.

What we have now is the following: to any $f\in C^\infty(\mathcal{M})$
we can assign a Hamiltonian vector field
$X_f\in \mathfrak{X}(\mathcal{M})$ whose flow $\Phi^f_\tau$ is a
symplectomorphism that preserves $f$. Now if we work locally in Darboux
coordinates $(q^\mu,p_\mu)$, so that
$\omega = \mathrm{d}q^\mu\wedge \mathrm{d}p_\mu$. If we write $X_f$
locally as

$$\label{eq:20}
  X_f = A^\mu{\frac{\partial }{\partial q^\mu}} + B_{\nu}{\frac{\partial }{\partial p_\nu}},$$
  
then we have that

$$\label{eq:21}
  \begin{aligned}
    \iota_{X_f}\omega &= \iota_{X_f}\left(\mathrm{d}q^\mu\wedge \mathrm{d}p_\mu\right)\\
    &= \mathrm{d}q^\mu(X_f)\mathrm{d}p_\mu - \mathrm{d}q^\mu\mathrm{d}p_\mu(X_f)\\
    &= A^\mu\mathrm{d}p_\mu - B_\mu\mathrm{d}q^\mu = \mathrm{d}f.
  \end{aligned}$$

However, since

$$\mathrm{d}f = {\frac{\partial f}{\partial q^\mu}}\mathrm{d}q^\mu + {\frac{\partial f}{\partial p_\mu}}\mathrm{d}p_\mu,$$


then necessarily the components of $X_f$ must be

$$\label{eq:22}
  \begin{aligned}
    A^\mu &= {\frac{\partial f}{\partial p_\mu}}\\
    B_\mu &= -{\frac{\partial f}{\partial q^\mu}}\\
  \end{aligned}.$$

The Hamiltonian vector field associated to $f$ is
then, in Darboux coordinates,

$$\label{eq:23}
  X_f = {\frac{\partial f}{\partial p_\mu}}{\frac{\partial }{\partial q^\mu}} -{\frac{\partial f}{\partial q^\mu}}{\frac{\partial }{\partial p_\mu}} = {\left\{-,f\right\}}.$$

And once again, if we choose $p_\nu =f$, then the Hamiltonian vector
field is

$$\label{eq:24}
  X_{p_\nu} = {\frac{\partial }{\partial q^\nu}},$$

So that the flow of
$X_{p_\nu}$ is simply translation along the $q^\nu$ coordinate. Once
again, we can say that the \[Hamiltonian vector field associated to
the\] canonical momentum is the generator of translations.

The takeaway 
============

We proved a general result in classical mechanics: to any observable
$f$, we can assign a differential operator $$X_f=\left\{-,f\right\}$$,
called the infinitesimal generator or Hamiltonian vector field
associated to $f$, that *generates* canonical transformations that
preserve $f$. The one-parameter group of canonical transformations
associated to $X_f$ is given by $\Phi^f_\tau = \exp(\tau X_f)$, and we
say that $f$ is the generator of $\Phi^f$.

In particular, if we choose the canonical momentum $p$ to be the
observable $f$, then the infinitesimal generator is
$X_p = \frac{\mathrm{d}}{\mathrm{d}q}$ and the group of canonical
transformations associated to $X_p$ is precisely the group of
translations of the $q$ coordinate. Therefore, we can say that **the
momentum is the generator of translations**.

Now in quantum mechanics, we simply **define** the momentum operator
$\hat{p}$ to be the infinitesimal generator of the unitary group of
translations, and we see that this definition is consistent with
canonical quantization.

References
----------

-   Sakurai, J. J. (1995). *Modern Quantum Mechanics, Revised Edition*.

-   Goldstein, H. , Poole, C. & Safko, J. (2001). *Classical Mechanics,
    Third Edition*.

-   José, J. V. & Saletan, E. (1998). *Classical Dynamics: A
    Contemporary Approach*. This book is great. I love it. Read it.

-   Abraham, R. & Marsden, J. (2008). *Foundations of Mechanics*.

Great thanks to Laura Arboleda for checking style and consistency.

[^1]: That is, it is a one-parameter absolutely continuous group.

[^2]: And an additional question that I would like to explore is “what’s
    the huge deal about canonical transformations”? We know that they
    preserve the structure of the Hamilton-Jacobi equations, but not
    necessarily the Hamiltonian, so that doesn’t seem like much, does
    it? Well it turns out that the *structure* itself of the equations
    has an interesting and beautiful mathematical background... But I’m
    saving that for later.
