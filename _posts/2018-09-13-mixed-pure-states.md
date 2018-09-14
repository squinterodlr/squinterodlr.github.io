---
author:
- Santiago Quintero de los Ríos
title: A few words on mixed and pure states
excerpt: I see that there is a bit of confusion between mixed and pure states in quantum mechanics. This is because the measurement of arbitrary observables for **pure states** is probabilistic, and this is easily confused with the probabilitites associated to a **mixed state**.
categories:
 - quantum mechanics
 - a few words
tags:
 - quantum mechanics
 - probability
 - statistical physics
mathjax: true

---
Get this post in [pdf format here](/assets/docs/pdf_posts/mixed-pure-states.pdf).

I see that there is a bit of confusion between mixed and pure states in
quantum mechanics. This is because the measurement of arbitrary
observables for **pure states** is probabilistic, and this is easily
confused with the probabilitites associated to a **mixed state**.

So let’s begin with the probabilistic nature of measurement of
observables of **pure** states.

Pure states
-----------

Let $\mathcal{H}$ be a Hilbert space (which for our sanity, we will
assume finite-dimensional, of dimension $N$). Any given vector
$\left\vert \psi\right\rangle$ is a **pure state**. For example, in the
spin-$1/2$ case, both $\left\vert +\right\rangle$ and $\left\vert -\right\rangle$
are pure states, but also any complex-linear combination of them is a
pure state (since these two vectors span all of $\mathcal{H}$).

Now let $A$ be an observable with associated hermitian operator
$\hat{A}$. Suppose that $\hat{A}$ has a set of orthonormal eigenstates
$\{\left\vert a_1\right\rangle,\dots,\left\vert a_n\right\rangle\}$. This means
that $\hat{A}\left\vert a_k\right\rangle = a_k\left\vert a_k\right\rangle$.
Assuming that the spectrum does not have any degeneracies (i.e. repeated
eigenvalues), then given any arbitrary state $\left\vert \psi\right\rangle$,
the **probability** of obtaining the value $a_k$ when measuring the
observable $A$ is

\begin{equation}P(A=a_k\vert \psi) = \left\vert \left\langle a_k\right\vert \psi\rangle\right\vert ^2.\end{equation}

Here we used standard notation from probability, and we explicitly wrote
$P(A=a_k\vert \psi)$ as a conditional probability, since this is the
probability to measure the value $a_k$ of the observable $A$ *given the
fact* that we **know** that the system is in state $\vert \psi\rangle$. Note
that applying this equation to $\vert \psi\rangle = \vert a_j\rangle$ for some
$j$, we obtain

\begin{equation}P(A=a_k\vert a_j) = \left\vert \left\langle a_k\right\vert a_j\rangle\right\vert ^2 = \delta_{kj}.\end{equation}

This is perfectly consistent with the axioms of quantum mechanics. If we
measure the observable $A$ **knowing** that the system is in the
eigenstate $\vert a_j\rangle$, then we are absolutely *certain* that the
measurement will return the value $a_j$. However, if the state is
**not** an eigenstate of $\hat{A}$, then we have *uncertainty* about
what the measurement will return. This (un)certainty is what the
probability $P(A=a_k\vert \psi)$ represents.

Then **even if we are absolutely certain that the system is in a given
state**, there is uncertainty regarding the outcome of (most)
experiments.

But what if we are not even certain about what state the system is in?
That’s where mixed states come in.

Mixed states {#sec:mixed-states}
------------

Imagine the following machine: It can emit a particle randomly in *one*
of two different states $\vert \psi_1\rangle,\vert \psi_2\rangle$, each state
$\vert \psi_j\rangle$ with probability $p_j$. After being emitted, the
particle travels to a detector which measures the observable $A$. After
the machine shoots a particle, we are *uncertain* about what the state
of the particle is. It might be in state $\vert \psi_1\rangle$ or in state
$\vert \psi_2\rangle$, the point is that *we don’t know*. In this case we say
that the system is in a **mixed state**. Compare this to the case of the
previous section, where we were *absolutely* certain that the particle
was in a specific state (this might be achieved by *preparing the
system* first, e.g. via a measurement).

Now we ask: After the random machine shoots a particle, what is the
probability of measuring the value $a_k$ for the observable $A$?

We can make use of a bit of probability theory and *marginalize*. We are
absolutely certain that the particle will be in **one** of the states
$\vert \psi_j\rangle$, but we don’t know which one. The event “the observed
value of $A$ is $a_k$” is then trivially equivalent to the two events
1.  The observed value of $A$ is $a_k$, AND
2.  the particle is either in state $\vert\psi_1 \rangle $ or in state
    $\vert\psi_2 \rangle$.

Of course, statement 2 is rather trivial. But both statements can be
written simultaneously as

\begin{equation}(A=a_k)\wedge(\vert \psi\rangle=\vert \psi_1\rangle \vee \vert \psi\rangle=\vert \psi_2\rangle).\end{equation}

We now use the distributive property of conjunction and disjunction
$( p \wedge (q\vee r) \Leftrightarrow (p\wedge q)\vee (p\wedge r))$ and
obtain that our statement is equivalent to

\begin{equation}(A=a_k\wedge\vert \psi\rangle=\vert \psi_1\rangle) \vee (A=a_k\wedge\vert \psi\rangle=\vert \psi_2\rangle).\end{equation}

Then the probability that we measure $a_k$ is equal to the probability
that
1.  The observed value of $A$ is $a_k$ AND the state is
    $\vert\psi_1\rangle$, OR
2.  the observed value of $A$ is $a_k$ AND the state is
    $\vert\psi_2\rangle$.
Therefore:

\begin{equation}P(A=a_k) = P(A=a_k\wedge\vert \psi\rangle=\vert \psi_1\rangle) + P(A=a_k\wedge\vert \psi\rangle=\vert \psi_2\rangle).\end{equation}

But now we use the **definition** of conditional probability:
$P(A\wedge B)=P(A\vert B)P(B)$, that is, the probability both $A$ and $B$
occur is the probability that $B$ occurs times the probability that $A$
occurs given the fact that we know that $B$ occurs. Using this
definition, the previous equation becomes (I’m dropping the $A=...$ and
$\vert \psi\rangle =...$ parts)

$$\begin{aligned}P(A=a_k) &= P(a_k\vert~\vert \psi_1\rangle)P(\vert \psi_1\rangle) + P(a_k\vert~\vert \psi_2\rangle)P(\vert \psi_2\rangle)\\ &= {\color{blue}p_1}{\color{purple}P(a_k\vert~\vert \psi_1\rangle)} + {\color{blue}p_2}{\color{purple}P(a_k\vert~\vert \psi_2\rangle)}\\
 &= {\color{blue}p_1}{\color{purple}\vert \langle a_k\vert\psi_1\rangle\vert ^2} + {\color{blue}p_2}{\color{purple}\vert \langle a_k\vert\psi_2\rangle\vert ^2} \end{aligned}$$

Here we can identify **two different sources of uncertainty**.<font color="#0000FF"> The
first one is purely quantum-mechanical. This uncertainty cannot be
eliminated, even with **perfect information** about the state of the
system</font>. <font color="#800080">The second one is associated with our imperfect knowledge of
the system, and it can be reduced with better information about its
state</font>. For example, if we were *certain* that the system is in state
$\vert \psi_1\rangle$, then $p_1=1$ and $p_2=0$, so that
$P(A=a_k) = P(A=a_k\vert \psi_1) = \vert \langle a_k \vert  \psi_1\rangle\vert ^2$, just as
in the case of a pure state.

All the previous discussion is generalized to the case of $m$ different
possible states, say $\vert \psi_1\rangle,\dots,\vert \psi_m\rangle$, with
probabilities $p_1,\dots,p_m$. In this case, the probability of
observing the value $a_k$ when measuring $A$ is

\begin{equation}P(A=a_k) = \sum_{i=1}^m{\color{blue} p_i}{\color{purple}\vert \langle a_k\vert \psi_i\rangle\vert ^2}.\end{equation}

One matrix to rule them all
---------------------------

How do we represent mixed states mathematically? Suppose we have a mixed
state with possible outcomes $\vert \psi_1\rangle,\dots,\vert \psi_m\rangle$, and
probabilities $p_1,\dots,p_m$. Recall that (basically) the only things
that we actually measure and care about in quantum mechanics are the
*expectation values* of observables. The expectation value is just the
weighed average of the observable, so

$$\begin{aligned} \langle A \rangle_{\text{mixed}} &= \sum_{k} a_k P(A=a_k)\\
  &= \sum_{k} a_k \sum_i p_i \vert \langle a_k \vert  \psi_i \rangle\vert ^2\\
  &= \sum_{k} a_k \sum_i p_i \langle a_k \vert  \psi_i \rangle\langle \psi_i \vert a_k\rangle\\
  &= \sum_{k} a_k \langle a_k \vert \left(\sum_i p_i  \vert \psi_i \rangle\langle \psi_i \vert \right) \vert a_k\rangle\\
  &= \sum_{k} \langle a_k \vert \left(\sum_i p_i  \vert \psi_i \rangle\langle \psi_i \vert \right) a_k \vert a_k\rangle\\
  &= \sum_{k} \langle a_k \vert \left(\sum_i p_i  \vert \psi_i \rangle\langle \psi_i \vert \right) \hat{A}\vert a_k\rangle\\
  &= \mathrm{Tr}\left(\hat{\rho}\hat{A}\right). \end{aligned}$$

Here we have assumed that the eigenstates of $\hat{A}$ form a complete
orthonormal basis, and we have defined **the density matrix**
$\hat{\rho}$ as

\begin{equation}\hat{\rho}:= \sum_i p_i  \vert\psi_i \rangle\langle \psi_i \vert.\end{equation}

With this matrix we can calculate the probability of measuring the value
$a_k$ of the observable $A$ in the mixed state as

\begin{equation}P(A=a_k) = \sum_{i=1}^m p_i\vert \langle a_k\vert \psi_i\rangle\vert ^2 = \langle a_k \vert  \left(\sum_{i=1}^mp_i\vert \psi_i\rangle\langle\psi_i\vert \right)\vert a_k\rangle = \langle a_k \vert \hat{\rho}\vert a_k\rangle,\end{equation}

which is the $k$-th diagonal element of the matrix $\hat{\rho}$ when
expressed in the basis of eigenstates of $\hat{A}$.

Note that $\mathrm{Tr}(\hat{\rho})=1$, and $\hat{\rho}$ is an hermitian
operator (i.e. $\hat{\rho}^{\dagger}=\hat{\rho}$, where $^{\dagger}$
denotes the conjugate transpose), therefore it can be diagonalized.
Furthemore, since for every vector $\vert \alpha\rangle$ we have that

\begin{equation}\langle \alpha \vert \hat{\rho}\vert \alpha\rangle = \sum_i p_i\vert \langle\alpha \vert \psi_i\rangle\vert ^2 \geq 0,\end{equation}

therefore $\hat{\rho}$ is positive semidefinite, so all of its
eigenvalues (let’s call them $\rho_1,\dots,\rho_N$) are non-negative.
Some of them might be zero, some might be repeated, but all are real and
non-negative. We have then, that:

\begin{equation}\mathrm{Tr}(\hat{\rho}) = \rho_1 + \cdots + \rho_N = 1,\end{equation}

so it follows that $0\leq\rho_k\leq 1$ for all $k=1,\dots,N$. This, in
turn, means that

\begin{equation}\mathrm{Tr}\left(\hat{\rho}^2\right) = \rho_1^2 + \cdots + \rho_N^2 \leq 1.\end{equation}

We have, then, that $\mathrm{Tr}\left(\hat{\rho}^2\right) = 1$ if and
*only if* $\rho_k=1$ for some $k$, and all the other $\rho_j = 0$ for
$j\neq k$. What this means is that **we are certain that the system is
in a particular state** $\vert \psi_k\rangle$, so, as in the first section,
the system is in a **pure state**. In this case, $1$ is an eigenvalue of
$\hat{\rho}$, then it must leave its eigenstate $\vert \psi\rangle$
invariant:

\begin{equation}\hat{\rho}\vert \psi\rangle = \vert \psi\rangle.\end{equation}

Now $\hat{\rho}$ cannot have any other (nonzero) eigenvalues, so it can
be written in the form

\begin{equation}\hat{\rho} = \vert \psi\rangle\langle\psi\vert .\end{equation}

This is the general form of the density matrix for a pure state. Recall
that, in this case $\mathrm{Tr}(\hat{\rho}^2)=1$, but for any other
case, the inequality is strict. This means that
$\mathrm{Tr}(\hat{\rho}^2)$ is, in some sense, **a measure of how
“pure”** the state is.

What we have just seen is that **the density matrix can represent both
mixed and pure states**, where pure states are of the form
$\hat{\rho}_{\text{pure}}=\vert \psi\rangle\langle\psi\vert $, whereas mixed
states are a **convex combination** of density matrices of pure states:

\begin{equation}\hat{\rho}\_{\text{mixed}} = \sum_{i=1}^m  p_i\hat{\rho}\_{i,\text{pure}},\end{equation}

with $p_1+\dots+p_m = 1$.

An example {#sec:an-example}
----------

Consider the case of spin-$1/2$. Suppose that we are in a mixed state of
$\vert +z\rangle$ with probability $p$ and $\vert -z\rangle$ with probability
$1-p$. The density matrix for this mixed state is

\begin{equation}\hat{\rho} = p\vert +z\rangle\langle +z \vert  + (1-p)\vert -z\rangle\langle -z \vert .\end{equation}

In this $z$-basis, the matrix takes the rather simple form

$$\hat{\rho} =
  \begin{pmatrix}
    p & 0\\
    0 & 1-p
  \end{pmatrix},$$

so that the square is simply

$$\hat{\rho}^2 =
  \begin{pmatrix}
    p^2 & 0\\
    0 & 1-2p+p^2
  \end{pmatrix}.$$

Then we have that

\begin{equation}\mathrm{Tr}\left(\hat{\rho}^2\right) = 2p^2 -2p + 1.\end{equation}

We could say that $I(\hat{\rho}) = 1-\mathrm{Tr}\left(\hat{\rho}^2\right)$ is a
measurement of how **impure** the state is: if this quantity is zero,
then the state is pure. The maximum of $I(\hat{\rho})$ occurs when
$p=1/2$, which is precisely when there is maximum uncertainty about the
state,

\begin{equation}\hat{\rho} = \frac{1}{2}\vert +z\rangle\langle +z \vert  + \frac{1}{2}\vert -z\rangle\langle -z \vert .\end{equation}

The state that this matrix represents is not, I repeat, **not** the same
as the “superposed” state

\begin{equation}\vert +x\rangle = \frac{1}{\sqrt{2}}\left(\vert +z\rangle + \vert -z\rangle\right).\end{equation}

Let’s analyze the similarities and the differences between the two.

The two states seem quite similar at first: They seem to be “equal
parts” $\vert +z\rangle$ and $\vert -z\rangle$. Furthermore, and probably most
importantly, the probability distribution of the $z$-spin observable $\hat{S}\_z$
is *the same* for both states. For a refresher, (assuming
for god’s sake that $\hslash = 1$), the $\vert \pm z\rangle$ states are
precisely the eigenstates of $\hat{S}\_z$ with eigenvalues
$\pm\frac{1}{2}$:
\begin{equation}\hat{S}_z\vert \pm z\rangle = \pm\frac{1}{2}\vert \pm z\rangle.\end{equation}
Therefore in our mixed state represented by $\hat{\rho}$,

\begin{equation}P\left(S_z = \pm\frac{1}{2}\right)_{\text{mixed}} = \langle \pm z \vert  \hat{\rho} \vert  \pm z\rangle = \frac{1}{2}.\end{equation}

Similarly, for the “superposed state” $\vert +x\rangle$, we have:

\begin{equation}P\left(S_z = \pm \left.\frac{1}{2} \right\vert  +x \right) = \vert \langle \pm z \vert  +x \rangle\vert ^2 = \frac{1}{2}.\end{equation}

This means that **if we only were able to measure** $S_z$, then the two
states would indeed be indistinguishable. However, *there are other
observables* that distinguish the half-and-half mixed state represented
by $\hat{\rho}$ and the “superposed” state $\vert +x\rangle$. A crystal-clear
observable that can distinguish between the two is the $x$-spin
observable, $S_x$. On one hand, for the mixed state $\hat{\rho}$,

\begin{equation}P\left(S_x = \frac{1}{2}\right)_{\text{mixed}} = \langle +x \vert \hat{\rho} \vert  +x \rangle = \frac{1}{2}.\end{equation}

However, for the superposed state:

\begin{equation}P\left(S_x = \left.\frac{1}{2} \right\vert  +x \right) = \vert \langle +x \vert  +x \rangle\vert ^2 = 1.\end{equation}

Furthermore, if we write the density matrix for the state $\vert +x\rangle$,
i.e. $\hat{\rho}_{+x}=\vert +x\rangle\langle +x\vert $, it passes the purity test
with flying colors: $$\mathrm{Tr}\left(\hat{\rho}_{+x}^2\right) = 1,$$
whereas, as we had already seen, for our mixed state
$\mathrm{Tr}(\hat{\rho}^2)=1/2$.

The takeaway
------------

The most important things to take away from all this are the following:
1.  There is **always** uncertainty in the measurement of observables in
    quantum mechanics, even if you are **absolutely certain** that the
    system is in a specific state. This uncertainty is **not** a
    consequence of systematic or instrumental errors, or lack of
    information about the system. In this case of absolute certainty, we
    say that the system is in a **pure state**.
2.  When we are not sure of what state the system is in, we represent
    our lack of knowledge by writing down a probability distribution on
    the set of probable states. Mathematically, we say that we know with
    probability $p_i$ that the system is in a state
    $\vert\psi_i\rangle$, and say that the system is in a **mixed
    state**. In this case, there is an *additional* uncertainty in the
    measurement of observables that comes from our *lack of knowledge*
    of the precise state that the system is in.
3.  Both pure and mixed states can be represented mathematically with a
    **density matrix**. This matrix has a lot of neat properties that
    make calculations of expectation values quite easy, even in the case
    of mixed states.

### References

1.  Most of this was inspired by a set of lectures that were given by
    dr. [Stefan Vandoren](http://www.staff.science.uu.nl/~vando101/)
    during the Summer School in Theoretical Physics at Utrecht
    University in 2018.
2.  Ballentine, Leslie E. 1990. *Quantum Mechanics*.
