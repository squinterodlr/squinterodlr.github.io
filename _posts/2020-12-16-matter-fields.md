---
title: "What is a gauge field? Part 2: Matter Fields"
excerpt: "What happens if we add a particle to an electromagnetic field?
What does it look like in the quantum case? What role do the potentials play in the evolution of the particle?"
categories:
    - gauge-fields
tags:
    - gauge-fields
mathjax: true
aside:
  toc: true
key: gauge-fields-02
---

Get this post on [pdf here](/assets/docs/pdf_posts/matter-fields.pdf).

[A long time
ago](/gauge-fields/2019/09/06/gauge-fields-01.html),
we showed that a "quicker" way to solve Maxwell's equations (at least in
the vacuum)
is by writing the fields $\mathbf{E}$ and $\mathbf{B}$ in terms of
electromagnetic potentials $\varphi$ and $\mathbf{A}$ which satisfy


$$\begin{aligned}
  \mathbf{B} &= \mathbf{\nabla}\times\mathbf{A};\\
  \mathbf{E} &= -\mathbf{\nabla}\varphi-\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t}.\end{aligned}$$


These potentials are not uniquely determined: given a smooth function
$\Lambda$, we can define new potentials as 

$$\begin{aligned}
  \mathbf{A}' &= \mathbf{A} +\mathbf{\nabla}\Lambda,\\
  \varphi' &= \varphi - \frac{1}{c}\frac{\partial \Lambda}{\partial t},\end{aligned}$$

and these give rise to the *same* electric and magnetic fields
$\mathbf{E}$, $\mathbf{B}$.

We want to see what happens if we add a test particle, and our end goal
is seeing at how it looks in the *quantum case*. What role do the potentials play in the evolution of the particle?

A particle of charge $e$ moving in an electric field $\mathbf{E}$ and a
magnetic field $\mathbf{B}$ feels a force given by


$$\mathbf{F}_{\text{Lor}} = e\left(\mathbf{E}+ \frac{1}{c}\mathbf{v}\times \mathbf{B}\right),$$


where $\mathbf{v}$ is the velocity of the particle. This force, called
the **Lorentz force**, is a vector function that depends on the position
$\mathbf{x}$ and velocity $\mathbf{v}$ of the particle, and possibly on
time (if the fields $\mathbf{B}$, $\mathbf{E}$ do).

If we wanted to introduce the Lorentz force to a quantum-mechanical
system, we would need a Hamiltonian $H$ such that the Hamilton equations
of motion

$$\begin{aligned}
  \dot{q}^i &= \frac{\partial H}{\partial p_i}\\
  \dot{p}_i &= -\frac{\partial H}{\partial q^i}\end{aligned}$$

are equivalent to the usual Newtonian equations of motion

$$m\ddot{\mathbf{x}} = \mathbf{F}_{\text{Lor}}.$$

With this Hamiltonian,
we would apply our favorite quantization rules.

But how do we find such a Hamiltonian? The best way to do so is to write
the Lorentz force in terms of a Lagrangian, and then do the Legendre
transform to obtain a Hamiltonian.

The classical case
==================

Here's where the *gauge fun* begins. Choose a pair of potentials
$\varphi,\mathbf{A}$ for $\mathbf{E},\mathbf{B}$. These satisfy


$$\begin{aligned}
  \mathbf{B} &= \mathbf{\nabla}\times\mathbf{A};\\
  \mathbf{E} &= -\mathbf{\nabla}\varphi-\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t}.\end{aligned}$$

It can be shown (and we do so below in the last section) that a
Lagrangian for the Lorentz force is given by

$$L(\mathbf{x},\mathbf{v},t) = \frac{1}{2}m\|\mathbf{v}\|^2 -e\varphi(\mathbf{x},t)+\frac{e}{c}\mathbf{v}\cdot \mathbf{A}(\mathbf{x},t).$$

Of course, one way to "prove" that this is a Lagrangian for the Lorentz
force is simply showing that the Euler-Lagrange equations are precisely
the equations of the Lorentz force. But that's really *ad hoc*, and
in [the gory details](#finding-the-lagrangian) below we show a more "natural" derivation.

From the Lagrangian, we see that the canonical momenta conjugate to the
positions $\mathbf{x}$ are

$$p_i =\frac{\partial L}{\partial \dot{x}^i}= m\dot{x}^i+\frac{e}{c}A^i,$$

so 

$$\mathbf{p} = m\dot{\mathbf{x}} + \frac{e}{c}\mathbf{A}.$$

Note that
$\mathbf{p}$ depends *explicitly* on the vector potential $\mathbf{A}$,
which is a sign that it is *not* a physical quantity, since we can
change the potential $\mathbf{A}$ to another physically equivalent one.
This means that we shouldn't be able to measure $\mathbf{p}$, since
$\mathbf{A}$ is not uniquely determined. We will return to this issue of
*physical quantities* later.

With the Legendre transform, we can find the Hamiltonian (this is just a
computation, no tricks involved):

$$H(\mathbf{x},\mathbf{p},t) = \dot{\mathbf{x}}\cdot \mathbf{p} - L = \frac{1}{2m}\left\|\mathbf{p}-\frac{e}{c}\mathbf{A}(\mathbf{x},t)\right\|^2 + e\varphi(\mathbf{x},t).$$

<div style="text-align: center"><img src="/assets/images/Objection.png" width="256" /></div>

The Hamiltonian (and the Lagrangian too) has an explicit dependence on
the potentials $\varphi, \mathbf{A}$, whereas the Lorentz force is only
dependent on the fields $\mathbf{E}$ and $\mathbf{B}$. If we change the
potentials via a gauge transformation, the Lorentz force doesn't change,
but the Lagrangian does! So there's something funky going on here. How
do we reconcile this?

Well, the Lagrangian changes, but the equations of motion don't. Let's
see this explicitly: let $\Lambda$ be a smooth (time-dependent) function
and let's do the gauge transformation 

$$\begin{aligned}
  \mathbf{A}' &= \mathbf{A}+\mathbf{\nabla}\Lambda\\
  \varphi' &=\varphi-\frac{1}{c}\frac{\partial \Lambda}{\partial t}.\end{aligned}$$

Substituting in the Lagrangian and doing a little reordering, we obtain

$$L'(\mathbf{x},\mathbf{v},t) = \frac{1}{2}m\|\mathbf{v}\|^2 -e\varphi(\mathbf{x},t)+\frac{e}{c}\mathbf{v}\cdot \mathbf{A}(\mathbf{x},t) +\frac{e}{c}\left(\mathbf{v}\cdot\mathbf{\nabla}\Lambda  +\frac{\partial \Lambda}{\partial t}\right) := L(\mathbf{x},\mathbf{v},t) + \frac{e}{c}\frac{\mathrm{d}\Lambda}{\mathrm{d}t}.$$

Here, we have defined $L'$ as $L$ but with $\varphi'$ and $\mathbf{A}'$
instead of $\varphi,\mathbf{A}$, and we have defined the total
derivative of $\Lambda$ as


$$\left(\frac{\mathrm{d}\Lambda}{\mathrm{d}t}\right)(\mathbf{x},\mathbf{v},t):= \mathbf{v}\cdot\mathbf{\nabla}\Lambda  +\frac{\partial \Lambda}{\partial t}.$$

This total derivative coincides with the derivative obtained from the
chain rule, if we evaluate it on $\mathbf{x}(t),\dot{\mathbf{x}}(t),t$
for a curve $\mathbf{x}:\mathbb{R}\to \mathbb{R}^3$. That is,


$$\left(\frac{\mathrm{d}\Lambda}{\mathrm{d}t}\right)(\mathbf{x}(t),\dot{\mathbf{x}}(t),t)= \frac{\mathrm{d}}{\mathrm{d}t}(\Lambda(\mathbf{x}(t),t)).$$

Therefore, our transformed Lagrangian has the form

$$L' = L + \frac{\mathrm{d}F}{\mathrm{d}t}$$

with $F=(e/c)\Lambda$. This
tells us that the Lagrangian itself is not gauge-invariant; however,
since it transforms up to a *total derivative*, the equations of motion
are invariant. We show this below in the [gory details](#gauge-invariance-of-the-equations-of-motion).

What about the Hamiltonian picture? First, let's see what happens to the
canonical momenta. Under a gauge transformation, they transform as

$$p'_i = \frac{\partial L'}{\partial \dot{x}^i} = \frac{\partial L}{\partial \dot{x}^i} +\frac{\partial }{\partial \dot{x}^i}\left(\frac{\mathrm{d}F}{\mathrm{d}t}\right) = p_i +\frac{\partial F}{\partial x^i}.$$

Therefore, the canonical momentum changes under a change of gauge as
$\mathbf{p}'=\mathbf{p}+\mathbf{\nabla}F$. If we perform the Legendre
transform of $L'$, we obtain a Hamiltonian in terms of this new
canonical momentum $\mathbf{p}'$

$$H'(\mathbf{x},\mathbf{p}',t) = \dot{\mathbf{x}}(\mathbf{p}')\cdot\mathbf{p}' - L'(\mathbf{x},\dot{\mathbf{x}}(\mathbf{p}'),t);$$

where we have made it explicit that we must write $\dot{\mathbf{x}}$ in
terms of $\mathbf{p}'$ and not $\mathbf{p}$. Carrying out the
computation we obtain

$$H'(\mathbf{x},\mathbf{p}',t) =\frac{1}{2m}\left\|\mathbf{p}'-\frac{e}{c}\mathbf{A}'(\mathbf{x},t)\right\|^2 + e\varphi'(\mathbf{x},t).$$

Does this mean that the Hamiltonian is gauge invariant? *No, it does
not*. This Hamiltonian is written in terms of the new momentum
$\mathbf{p}'$, and we need to see how it relates to the Hamiltonian with
the old momentum $\mathbf{p}$. So we substitute all the new momenta and
potentials in terms of the old: 

$$\begin{aligned}
  H'(\mathbf{x},\mathbf{p}',t) &= \frac{1}{2m}\left\|\mathbf{p} + \frac{e}{c}\mathbf{\nabla}\Lambda -\frac{e}{c}\mathbf{A} -\frac{e}{c}\mathbf{\nabla}\Lambda \right\|^2 + e\varphi(\mathbf{x},t) -\frac{e}{c}\frac{\partial \Lambda}{\partial t}\\
                         &= \frac{1}{2m}\left\|\mathbf{p}-\frac{e}{c}\mathbf{A}\right\|^2 + e\varphi(\mathbf{x},t) -\frac{e}{c}\frac{\partial \Lambda}{\partial t}\\
                         &= H(\mathbf{x},\mathbf{p},t) -\frac{e}{c}\frac{\partial \Lambda}{\partial t}.\end{aligned}$$

Thus, the Hamiltonian is in general *not* gauge-invariant! But once
again, the day is saved since Hamilton's *equations of motion* are.
Again, we leave this to the [gory details](gauge-invariance-of-the-equations-of-motion).

In conclusion, even though the Lagrangian and Hamiltonian are explicitly
dependent on the potentials, and therefore *not* gauge-invariant, the
equations of motions *are* gauge-invariant, so the dynamics of the
system are well-defined. This is to be expected, since both the
Lagrangian and the Hamiltonian picture are equivalent to Newton's
equations of motion, which do not even include the potentials
explicitly.

The quantum case
================

Now that we have a Hamiltonian, we can write the Schrödinger equation

$$i\hslash \frac{\partial \psi}{\partial t} = H\psi = \frac{1}{2m}\left(\mathbf{p}-\frac{e}{c}\mathbf{A}\right)^2\psi + e\varphi\psi.$$


Here comes another problem: The Hamiltonian is dependent on the choice
of potential! But this time we can't shield ourselves under the "don't
worry, the equations of motion are safe" that we used in the last
section, since the Schrödinger equation *is* the equation of motion! So
there's nothing stopping the evolution of the wavefunction $\psi$ from
depending on the choice of potential!

But we *do* have one more trick under our sleeve. The wavefunction is
not the measurable object, but rather its square norm $|\psi|^2$, and in
general the *expectation values*[^1] of Hermitian operators $\hat{O}$


$$\left\langle \psi\middle|\hat{O} \middle\vert \psi\right\rangle.$$


This means that we can save this Hamiltonian if we guarantee that
whenever we change the potentials to some new ones
$\mathbf{A}',\varphi'$ (via some gauge transformation), then every
solution $\psi$ of the Schrödinger equation and every observable
$\hat{O}$ have *physically equivalent* solutions $\psi'$ (to the
Schrödinger equation with the new potentials) and observables $\hat{O}'$
such that


$$\left\langle \psi'\middle|\hat{O}' \middle\vert \psi'\right\rangle=\left\langle \psi\middle|\hat{O} \middle\vert \psi\right\rangle.$$


One way to guarantee this is with unitary transformations. Suppose that
$\psi$ is a solution to the Schrödinger equation with potentials
$\varphi,\mathbf{A}$. Now let $\Lambda$ be a smooth function and let
$\varphi',\mathbf{A}'$ be the gauge-transformed potentials


$$\begin{aligned}
  \mathbf{A}'&=\mathbf{A}+\nabla\Lambda\\
  \varphi' &= \varphi -\frac{1}{c}\frac{\partial \Lambda}{\partial t}.\end{aligned}$$

Suppose that there exists a unitary transformation $U(\Lambda)$
associated to $\Lambda$ such that the new "gauge-transformed"
wavefuntion 

$$\begin{aligned}
  \psi' &= U\psi\end{aligned}$$
 is a solution of the Schrödinger
equation with the potentials $\varphi',\mathbf{A}'$. If for every
observable $\hat{O}$ we define 

$$\hat{O}' = U\hat{O}U^{-1},$$

then necessarily

$$\left\langle \psi'\middle|\hat{O}' \middle\vert \psi'\right\rangle=  \left\langle U\psi\middle|U\hat{O}U^{-1} \middle\vert U\psi\right\rangle=\left\langle \psi\middle|U^{\dagger}U\hat{O} \middle\vert \psi\right\rangle= \left\langle \psi\middle|\hat{O} \middle\vert \psi\right\rangle.$$

This follows from the fact that $U^\dagger U = I$, since $U$ is unitary.

Now we have a problem. The rule $\hat{O}\mapsto U\hat{O}U^{-1}$ gives us
a way to transform observables between different gauges. However, we may
already have a definition of the observable in a different gauge! For
example, if we write the momentum operator $\mathbf{p}$ in the position
representation, it becomes $-i\hslash\nabla$. This definition *should*
be the same for *all* gauges, since changing gauges does not alter the
coordinates. That means that we define

$$\mathbf{p}_{\mathbf{A},\varphi} = \mathbf{p}_{\mathbf{A}',\varphi'}\overset{\text{position rep.}}{:=}-i\hslash\nabla$$

for all potentials[^2]. However, we also have a gauge transformation
rule that tells us how operators transform between gauges. Do these
prescriptions agree with one another? That is, do we have

$$U\mathbf{p}_{A,\varphi}U^{-1} \overset{?}{=}\mathbf{p}_{\mathbf{A}',\varphi'}$$

As we will see below, the answer is **no**, since, assuming that $U$
depends only on positions and not momenta,

$$U\mathbf{p}_{A,\varphi}U^{-1} = \mathbf{p}_{A,\varphi} + i\hslash (\nabla U)U^{-1}\neq \mathbf{p}_{A',\varphi'}.$$

There is a conflict between the transformation law and our *definition*
of the momentum operator between different gauges. This tells us that
the observable $\mathbf{p}$ is *not physical*, because the results of
observations cannot be defined consistently between gauges (and
remember, up to this point, the gauges are just mathematical tools).

In general, we say that an observable $\hat{O}$ is **physical** if its
definition in different gauges is consistent with the transformation
law. That is, if

$$U\hat{O}_{\mathbf{A},\varphi}U^{-1} = \hat{O}_{\mathbf{A}',\varphi'}.$$

Another example of an *un*physical observable is the potential
$\mathbf{A}$. If we assume that the unitary transformation $U$ depends
only on the position, then it commutes with $\mathbf{A}$, so

$$U\mathbf{A}U^{-1} = \mathbf{A} \overset{!}{\neq} \mathbf{A}'.$$

So how do we find $U(\Lambda)$? Does it even exist? In the [gory details](#finding-the-unitary-transformation)
below, we show that the correct unitary transformation is

$$U(\Lambda) = \exp\left(\frac{ie}{\hslash c}\Lambda\right),$$

so that the wavefunction $\psi$ transforms as

$$\psi' = \exp\left(\frac{ie}{\hslash c}\Lambda\right)\psi.$$

Let's check that $\psi'$ does indeed satisfy the Schrödinger equation with the
Hamiltonian with respect to the new gauge. We have 

$$\begin{aligned}
  i\hslash\frac{\partial \psi'}{\partial t} &= i\hslash\frac{\partial U(\Lambda)}{\partial t}\psi + i\hslash U(\Lambda)\frac{\partial \psi}{\partial t}\\
                         &= -\frac{e}{c}\frac{\partial \Lambda}{\partial t}\exp\left(\frac{ie}{\hslash c}\Lambda\right)\psi + U(\Lambda)\left(i\hslash\frac{\partial \psi}{\partial t}\right).\end{aligned}$$

By hypothesis $\psi$ satisfies the Schrödinger equation with the
potentials $\mathbf{A},\varphi$, so 

$$\begin{aligned}
  i\hslash\frac{\partial \psi'}{\partial t} &= -\frac{e}{c}\frac{\partial \Lambda}{\partial t}\psi' + U(\Lambda)\left( \frac{1}{2m}\left(\mathbf{p}-\frac{e}{c}\mathbf{A}\right)^2 + e\varphi\right)\psi.\end{aligned}$$

Now we note that

$$U(\Lambda)\mathbf{p}= \mathbf{p}U(\Lambda) + [U(\Lambda),\mathbf{p}]= \mathbf{p}U(\Lambda) + i\hslash\nabla U(\Lambda)= \mathbf{p}U(\Lambda) - \frac{e}{c}\nabla\Lambda U(\Lambda) = \left(\mathbf{p}-\frac{e}{c}\nabla\Lambda\right)U(\Lambda).$$

Therefore,

$$U(\Lambda)\left(\mathbf{p}-\frac{e}{c}\mathbf{A}\right)^2 = \left(\mathbf{p}-\frac{e}{c}\mathbf{A}-\frac{e}{c}\nabla\Lambda\right)^2U(\Lambda)$$

Since $U(\Lambda)$ depends only on position, then it commutes with
$\varphi$. Therefore, we obtain (after a little rearrangement)

$$\begin{aligned}
  i\hslash\frac{\partial \psi'}{\partial t} &= \frac{1}{2m}\left(\mathbf{p}-\frac{e}{c}\left(\mathbf{A}+\nabla\Lambda\right)\right)^2\psi' + e\left(\varphi-\frac{1}{c}\frac{\partial \Lambda}{\partial t}\right)\psi'\\
                         &= \frac{1}{2m}\left(\mathbf{p}-\frac{e}{c}\mathbf{A}'\right)^2\psi' + e\varphi'\psi'.\end{aligned}$$

Finally, we note that the definition of $\mathbf{p}$ is the same for all
gauges, so we write $\mathbf{p}' = \mathbf{p}$, and thus obtain

$$i\hslash\frac{\partial \psi'}{\partial t} = H_{\mathbf{A}',\varphi'}\psi'.$$

Therefore, the wavefunction
$\psi' = \exp\left(\frac{ie}{\hslash c}\Lambda\right)\psi$ satisfies the
Schrödinger equation with the gauge-transformed potentials $\varphi'$,
$\mathbf{A}'$. In the context of gauge theories, we call $\psi$ a
**matter field**.

Minimal coupling and covariant derivatives
==========================================

The Schrödinger equation for the particle coupled to an electromagnetic
field is not very different from the free equation. If we start with the
free equation

$$i\hslash\frac{\partial \psi}{\partial t} = \frac{1}{2m}\mathbf{p}^2\psi,$$

and make the changes 

$$\begin{aligned}
  \frac{\partial }{\partial t} &\mapsto \frac{\partial }{\partial t} +\frac{ie}{\hslash}\varphi,\\
  \mathbf{p} &\mapsto \mathbf{p} -\frac{e}{c}\mathbf{A},\end{aligned}$$

then we obtain the coupled equation

$$i\hslash \frac{\partial \psi}{\partial t} =  \frac{1}{2m}\left(\mathbf{p}-\frac{e}{c}\mathbf{A}\right)^2\psi + e\varphi\psi.$$

This is called the *minimal coupling* prescription.

These seem like arbitrary changes. However, if we write everything in
the unified four-dimensional framework we talked about last time, we'll
see that they are similar. Our four-dimensional coordinates are
$x^0 = ct$, $x^1=x$, $x^2=y$, $x^3=z$. We condense the fields and
potentials into four-dimensional differential forms: The potentials
become a one-form $A = A_\mu\mathrm{d}{x}^\mu$ with components

$$\begin{aligned}
  A_0 &= \varphi & A_i &= -\mathbf{A}^i,\end{aligned}$$

and the fields become a two-form
$F = \frac{1}{2}F_{\mu\nu}\mathrm{d}{x}^\mu\wedge\mathrm{d}{x}^\nu$ with
components 

$$\begin{aligned}
  F_{0i} &= \mathbf{E}^i & F_{ij} &= -\varepsilon_{ijk}\mathbf{B}^k,\end{aligned}$$

satisfying

$$F = \mathrm{d}{A}.$$

Under a gauge transformation, the
electromagnetic potential $A$ transforms as

$$A\mapsto A' = A -\mathrm{d}{\Lambda},$$

and of course the field strength $F$ remains invariant.

The minimal coupling prescription is now obtained by making the change

$$\partial_\mu \mapsto \mathscr{D}_\mu:= \partial_\mu +\frac{ie}{\hslash c}A_\mu.$$

The symbol $\mathscr{D}_{\mu}$ is called the *covariant derivative*.
Indeed, we can check that the compontents $\mathscr{D}_0$ and
$\mathscr{D}_i$ correspond to the operators
$\partial_t + \frac{ie}{\hslash}\varphi$ and
$\mathbf{p}-\frac{e}{c}\mathbf{A}$ that we discussed above.

Why do we care about this covariant derivative? If transform to a new
gauge $A'=A-\mathrm{d}{\Lambda}$, then the covariant derivative changes
as


$$\mathscr{D}_\mu\mapsto \mathscr{D}_\mu' =  \mathscr{D}_\mu -\frac{ie}{\hslash c}\partial_\mu\Lambda.$$

So it's not quite gauge-invariant on its own. However, when we let
$\mathscr{D}_\mu$ act on the wavefunction $\psi$, and apply a gauge
transformation to *both* at the same time, we get 

$$\begin{aligned}
  \mathscr{D}_\mu'\psi' &= \left(\mathscr{D}_\mu - \frac{ie}{\hslash c}\partial_\mu\Lambda\right)\exp\left(\frac{ie}{\hslash c}\Lambda\right)\psi\\
                        &=\partial_\mu\left(\exp\left(\frac{ie}{\hslash c}\Lambda\right)\psi\right) - \exp\left(\frac{ie}{\hslash c}\Lambda\right)\left(\frac{ie}{\hslash c}A_\mu\psi + \frac{ie}{\hslash c}\partial_\mu\Lambda \psi\right)\\
                        &=\exp\left(\frac{ie}{\hslash c}\Lambda\right)\left(\frac{ie}{\hslash c}\partial_\mu\Lambda \psi + \partial_\mu\psi - \frac{ie}{\hslash c}A_\mu\psi - \frac{ie}{\hslash c}\partial_\mu\Lambda \psi\right)\\
                        &=\exp\left(\frac{ie}{\hslash c}\Lambda\right)\mathscr{D}_\mu\psi\\
                        &=(\mathscr{D}_\mu\psi)'.\end{aligned}$$

Thus, after applying the covariant derivative to the wavefunction $\psi$, we
get another wavefunction which transforms properly under gauge
transformations. We call this gauge *covariance*: If apply the
gauge-transformed covariant derivative to the gauge-transformed matter
field, we get the same result as applying the un-transformed derivative
to the un-transformed field and *then* transforming the result.

The takeaway
============

We started with some *fields* $\mathbf{E}$ and $\mathbf{B}$ which could
be written in terms of some *potentials* $\mathbf{A}$, $\varphi$. The
potentials are *not* uniquely determined, since we can change them by a
*gauge transformation*, and the fields remain the same. The quantities
that are invariant under these gauge transformations are *physical*.

In quantum mechanics, the wavefunction $\psi$ and *physical* observables
$\hat{O}$ might be gauge-dependent, but under a gauge transformation,
they transform by a unitary transformation in a way that the expectation
values of physical observables are all invariant.

In summary, we have the following objects and how they transform under a
gauge transformation:

$$\begin{array}{ccl}
  \mathbf{A}& \mapsto & \mathbf{A}'   = \mathbf{A}+\nabla\Lambda\\[0.1em]
  \varphi   & \mapsto & \varphi'   = \displaystyle \varphi -\frac{1}{c}\frac{\partial \Lambda}{\partial t}\\
  \mathbf{E}& \mapsto & \mathbf{E}  \\
  \mathbf{B}& \mapsto & \mathbf{B}  \\
  \psi      & \mapsto & \psi'      = \displaystyle \exp\left(\frac{ie}{\hslash c}\Lambda\right)\psi\\[0.5em]
  \hat{O}   & \mapsto &  \hat{O}'  = \displaystyle \exp\left(\frac{ie}{\hslash c}\Lambda\right)\hat{O}\exp\left(-\frac{ie}{\hslash c}\Lambda\right).
\end{array}$$

Finally, we saw that an "easy" way to go from the free
theory to the minimally coupled theory is substituting ordinary
derivatives with covariant derivatives:

$$\partial_\mu\mapsto\mathscr{D}_\mu =  \partial_\mu + \frac{ie}{\hslash c}A_\mu.$$

This is how it is often done for more complicated gauge theories (which
we will explore later).

The next step is interpreting all these objects as *local*
representations of global objects in the theory of *principal bundles*.

The gory details
================

Finding the Lagrangian
----------------------

Substituting the expressions for $\mathbf{E}$ and $\mathbf{B}$ in terms
of the potentials $\varphi$ and $\mathbf{A}$ in the Lorentz force, we
obtain


$$\mathbf{F} = e\left(-\mathbf{\nabla}\varphi-\frac{1}{c}\frac{\partial \mathbf{A}}{\partial t} + \frac{1}{c}\mathbf{v}\times (\mathbf{\nabla}\times\mathbf{A})\right).$$

Now we use one of those super fun vector product identities,


$$\mathbf{a}\times(\mathbf{b}\times\mathbf{c}) = (\mathbf{a}\cdot\mathbf{c})\mathbf{b}-(\mathbf{a}\cdot\mathbf{b})\mathbf{c},$$

which becomes in our case


$$\mathbf{v}\times (\mathbf{\nabla}\times\mathbf{A}) = \mathbf{\nabla}(\mathbf{v}\cdot \mathbf{A}) - (\mathbf{v}\cdot\mathbf{\nabla})\mathbf{A}.$$

Therefore,


$$\mathbf{F} = e\left(-\mathbf{\nabla}\left(\varphi-\frac{1}{c}\mathbf{v}\cdot\mathbf{A}\right)  - \frac{1}{c}\left(\frac{\partial \mathbf{A}}{\partial t} +(\mathbf{v}\cdot\mathbf{\nabla})\mathbf{A}\right)\right).$$

Let's plug this into Newton's equation of motion. Let
$\mathbf{x}:\mathbb{R}\to \mathbb{R}^3$ be the trajectory of a particle
of mass $m$, and let $\dot{\mathbf{x}}$ be its velocity. Newton's second
law reads

$$m\ddot{\mathbf{x}}(t) = \mathbf{F}(\mathbf{x}(t),\dot{\mathbf{x}}(t),t) = e\left(-\mathbf{\nabla}\left(\varphi-\frac{1}{c}\dot{\mathbf{x}}\cdot\mathbf{A}\right)  - \frac{1}{c}\left(\frac{\partial \mathbf{A}}{\partial t} +(\dot{\mathbf{x}}\cdot\mathbf{\nabla})\mathbf{A}\right)\right).$$

It is important to note that here we are implicitly evaluating the
time-dependent fields $\varphi,\mathbf{A}$ at $(\mathbf{x}(t),t)$. In
particular, the rightmost term becomes, applying the chain rule,


$$\frac{\partial \mathbf{A}}{\partial t}(\mathbf{x}(t),t) +((\dot{\mathbf{x}}\cdot\mathbf{\nabla})\mathbf{A})(\mathbf{x}(t),t) = \frac{\mathrm{d}}{\mathrm{d}t}\mathbf{A}(\mathbf{x}(t),t).$$


Then Newton's second law becomes, in components,

$$m\ddot{\mathbf{x}}^i(t) = e\left(-\frac{\partial }{\partial x^i}\left(\varphi-\frac{1}{c}\sum_{k}\dot{\mathbf{x}}^k\mathbf{A}^k\right)-\frac{1}{c}\frac{\mathrm{d}}{\mathrm{d}t}\mathbf{A}^i(\mathbf{x}(t),t)\right).$$

Now comes the *dirty trick*. We can write $\mathbf{A}^i$ as

$$-\frac{1}{c}\mathbf{A}^i = -\frac{1}{c}\frac{\partial }{\partial \dot{x}^i}\left(\sum_{k}\dot{x}^k\mathbf{A}^k \right) = \frac{\partial }{\partial \dot{x}^i}\left(\varphi - \frac{1}{c}\sum_{k}\dot{x}^k\mathbf{A}^k \right).$$

Similarly, we can write $\ddot{\mathbf{x}}^i$ as


$$\ddot{\mathbf{x}}^i = \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial }{\partial \dot{x}^i}\frac{1}{2}\sum_{k}{\dot{x}^k}\dot{x}^k\right).$$

With these replacements, Newton's equation takes the form of an
Euler-Lagrange equation:


$$\frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial }{\partial \dot{x}^i}\frac{m}{2}\sum_{k}{\dot{x}^k}\dot{x}^k\right)= \frac{\partial }{\partial x^i}\left(-e\varphi+\frac{e}{c}\sum_{k}\dot{x}^k\mathbf{A}^k\right) +\frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial }{\partial \dot{x}^i}\left(e\varphi - \frac{e}{c}\sum_{k}\dot{x}^k\mathbf{A}^k \right).$$

Or, well, after a few rearrangements:


$$\frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial }{\partial \dot{x}^i}\left(\frac{m}{2}\sum_{k}{\dot{x}^k}\dot{x}^k -e\varphi + \frac{e}{c}\sum_{k}\dot{x}^k\mathbf{A}^k \right) - \frac{\partial }{\partial x^i}\left(\frac{m}{2}\sum_{k}{\dot{x}^k}\dot{x}^k -e\varphi + \frac{e}{c}\sum_{k}\dot{x}^k\mathbf{A}^k \right)=0.$$

Therefore, we can use the Lagrangian

$$L(\mathbf{x},\mathbf{v},t) = \frac{1}{2}m\|\mathbf{v}\|^2 -e\varphi(\mathbf{x},t)+\frac{e}{c}\mathbf{v}\cdot \mathbf{A}(\mathbf{x},t).$$


Gauge-invariance of the equations of motion
-------------------------------------------

Under a gauge transformation, the Lagrangian changes as

$$L' = L + \frac{\mathrm{d}F}{\mathrm{d}t}$$
 with $F=(e/c)\Lambda$.
Although the Lagrangian itself is not gauge-invariant, since it
transforms up to a *total derivative*, then the equations of motion are
invariant: 

$$\begin{aligned}
  \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial L'}{\partial \dot{x}^i}\right) - \frac{\partial L'}{\partial x^i} &= \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial L}{\partial \dot{x}^i}\right) - \frac{\partial L}{\partial x^i} +\frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial }{\partial \dot{x}^i}\frac{\mathrm{d}F}{\mathrm{d}t}\right) - \frac{\partial }{\partial x^i}\left(\frac{\mathrm{d}F}{\mathrm{d}t}\right)\\
                                                           &= \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial L}{\partial \dot{x}^i}\right) - \frac{\partial L}{\partial x^i} +\frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial F}{\partial x^i}\right) - \frac{\partial }{\partial x^i}\left(\frac{\mathrm{d}F}{\mathrm{d}t}\right)\\
                                                           &= \frac{\mathrm{d}}{\mathrm{d}t}\left(\frac{\partial L}{\partial \dot{x}^i}\right) - \frac{\partial L}{\partial x^i}.\end{aligned}$$

Here we used the fact that


$$\frac{\partial }{\partial \dot{x}^i}\left(\frac{\mathrm{d}F}{\mathrm{d}t}\right) =   \frac{\partial }{\partial \dot{x}^i}\left( \frac{\partial F}{\partial t} + \sum_k\dot{x}^k\frac{\partial F}{\partial x^k}\right) = \frac{\partial F}{\partial x^i}.$$


In the Hamiltonian picture, the canonical momenta transform as


$$\mathbf{p}'=\mathbf{p}+\mathbf{\nabla}F,$$
 and the Hamiltonian
transforms like

$$H'(\mathbf{x},\mathbf{p}',t) = H(\mathbf{x},\mathbf{p},t) -\frac{\partial F}{\partial t}.$$


Although the Hamiltonian is *not* gauge-invariant, the *equations of
motion* are. If we have a trajectory $\mathbf{x}(t)$, $\mathbf{p}(t)$
which satisfies 

$$\begin{aligned}
  \dot{\mathbf{x}}^i &= \frac{\partial H}{\partial p_i}\\
  \dot{\mathbf{p}}_i &= -\frac{\partial H}{\partial x^i},\end{aligned}$$

then it also satisfies 

$$\begin{aligned}
  \dot{\mathbf{x}}^i = \frac{\partial H}{\partial p_i} &= -\frac{\partial }{\partial p_i}\left(H'(\mathbf{x},\mathbf{p}',t)+\frac{\partial F}{\partial t}\right)\\
                                 &=\sum_{j}\frac{\partial H'}{\partial p'_j}\frac{\partial p'_j}{\partial p_i}\\
                                 &=\frac{\partial H'}{\partial p'_i}.\end{aligned}$$

The equations of motion for the momenta are more subtle. We have to note
that when we write $\mathbf{p'}=\mathbf{p}+\nabla F$, we are introducing
an *explicit* dependence of $\mathbf{p}'$ on the position variables
$x^i$. And so, we must be careful when applying the chain rule:


$$\begin{aligned}
  \dot{\mathbf{p}}'_i &= \dot{\mathbf{p}}_i + \frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial F}{\partial x^i}\\
                   &= -\frac{\partial H}{\partial x^i} + \frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial F}{\partial x^i}\\
                   &= -\frac{\partial }{\partial x^i}\left(H'(\mathbf{x},\mathbf{p}',t) +\frac{\partial F}{\partial t}\right) + \frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial F}{\partial x^i}\\
                   &=-\frac{\partial H'}{\partial x^i} -\sum_{j}\frac{\partial H'}{\partial p'_j}\frac{\partial p'_j}{\partial x^i} - \frac{\partial }{\partial x^i}\frac{\partial F}{\partial t} + \frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial F}{\partial x^i}\\
                   &=-\frac{\partial H'}{\partial x^i} -\sum_{j}\dot{\mathbf{x}}_j\frac{\partial }{\partial x^i}\frac{\partial F}{\partial x^j} - \frac{\partial }{\partial x^i}\frac{\partial F}{\partial t} + \frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial F}{\partial x^i}\\
                   &=-\frac{\partial H'}{\partial x^i}-\frac{\partial }{\partial x^i}\left(\sum_{j}\dot{\mathbf{x}}^j\frac{\partial F}{\partial x^j} +\frac{\partial F}{\partial t}\right) +\frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial F}{\partial x^i}\\
                   &=-\frac{\partial H'}{\partial x^i} -\frac{\partial }{\partial x^i}\frac{\mathrm{d}F}{\mathrm{d}t} +\frac{\mathrm{d}}{\mathrm{d}t}\frac{\partial F}{\partial x^i}\\
                   &=-\frac{\partial H'}{\partial x^i}.\end{aligned}$$

Then Hamilton's equations are preserved under the gauge transformation,
and so the dynamics of the system is the same independent of the chosen
gauge.

Finding the unitary transformation
----------------------------------

Suppose that $\psi$ is a solution to the Schrödinger equation

$$i\hslash \frac{\partial \psi}{\partial t} = \frac{1}{2m}\left(\mathbf{p}-\frac{e}{c}\mathbf{A}(\mathbf{x},t)\right)^2\psi + e\varphi(\mathbf{x},t)\psi,$$

and suppose that there is a unitary transformation $U(\Lambda)$ such
that $\psi' = U(\Lambda)\psi$ satisfies the Schrödinger equation with
the transformed potentials:

$$i\hslash \frac{\partial \psi'}{\partial t} = \frac{1}{2m}\left(\mathbf{p}'-\frac{e}{c}\mathbf{A}'(\mathbf{x},t)\right)^2\psi' + e\varphi'(\mathbf{x},t)\psi'.$$

Since $U(\Lambda)$ is unitary, it is a general fact[^3] that it can be
written as 
$$U(\Lambda) = \exp(iG(\Lambda))$$
 for some Hermitian
$G(\Lambda)$. In general, $G$ is going to be a function only of
$\mathbf{x}$ and $t$, since it depends only on $\Lambda$. We want to
find $G$.

Let's split the Schrödinger equation with transformed potentials into
little bits. On the left-hand side, we have

$$i\hslash \frac{\partial \psi'}{\partial t} = i\hslash\frac{\partial }{\partial t}(\exp(iG)\psi) = -\hslash\frac{\partial G}{\partial t}\exp(iG)\psi +i\hslash\exp(iG)\frac{\partial \psi}{\partial t}.$$

On the right-hand side, we use the fact that


$$\mathbf{p}U = U\mathbf{p} -i\hslash\nabla U = \exp(iG)\mathbf{p} +\hslash\nabla G \exp(iG),$$

so


$$\left(\mathbf{p}'-\frac{e}{c}\mathbf{A}'\right)^2\psi' = \left(\mathbf{p}'-\frac{e}{c}\mathbf{A}'\right)^2\exp(iG)\psi = \exp(iG)\left(\mathbf{p}'-\frac{e}{c}\mathbf{A}' +\hslash\nabla G\right)^2\psi.$$

If we write $\mathbf{A}'=\mathbf{A}+\nabla\Lambda$,
$\varphi' = \varphi -\frac{1}{c}\partial_t\Lambda$, and
$\mathbf{p'}=\mathbf{p}$, plug everything back in and reorder a little
bit, we obtain


$$\exp(iG)\left(i\hslash\frac{\partial \psi}{\partial t}\right) = \exp(iG)\left(\mathbf{p}-\frac{e}{c}\mathbf{A}-\frac{e}{c}\nabla \Lambda + \hslash\nabla G\right)^2\psi +\exp(iG)\varphi\psi + \exp(iG)\left(\hslash\frac{\partial G}{\partial t}-\frac{e}{c}\frac{\partial \Lambda}{\partial t}\right)\psi.$$

This equation looks like the Schrödinger equation for $\psi$, but with
an $\exp(iG)$ in front and a bunch of other things that we want to get
rid of. We would easily get rid of them if 

$$\begin{aligned}
  \hslash\nabla G &= \frac{e}{c}\nabla\Lambda\\
  \hslash\frac{\partial G}{\partial t} &= \frac{e}{c}\frac{\partial \Lambda}{\partial t}.\end{aligned}$$

This is a differential equation for $G$, which has an easy solution[^4]:

$$G = \frac{e}{\hslash c}\Lambda.$$
 Therefore, if we choose the unitary
transformation to be

$$U(\Lambda) = \exp\left(\frac{ie}{\hslash c}\right),$$
 then
$\psi' = U(\Lambda)\psi$ is a solution to the Schrödinger equation with
the potentials $\mathbf{A}'$, $\varphi'$ whenever $\psi$ is a solution
to the equation with potentials $\mathbf{A}$, $\varphi$.

References
==========

-   Landau, L. D. and Lifschitz, E. M. (1977). *Quantum Mechanics:
    Non-relativistic theory*. Chapter XV.

-   Sakurai, J.J. and Napolitano, J. (2011). *Modern Quantum Mechanics,
    Second Edition*, Section 2.7.

[^1]: We can obtain
    $|\left\langle \phi \middle\vert \psi\right\rangle|^2$ as the
    expectation value of the projection operator
    $\mathrm{pr}_{\psi}=\vert \psi \rangle\left\langle \psi \right\vert$
    in the $\phi$ state.

[^2]: This is in stark contrast from the Lagrangian case, where
    canonical momentum changes as the potentials change.

[^3]: See references. This is relatively easy to show in the
    finite-dimensional case, but quite non-trivial for general Hilbert
    spaces!

[^4]: Which is not unique, but that doesn't matter.
