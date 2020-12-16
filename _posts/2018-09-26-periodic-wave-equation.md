---
title: 'Mini-post: The periodic 1D wave equation'
excerpt: Wherein I very briefly discuss the general solution to the periodic 1D wave equation.
mathjax: true
show_author_profile: true
categories:
    - physics
tags:
    - PDE
key: wave-eqn
---

Get this post in [pdf format here](/assets/docs/pdf_posts/periodic-wave-equation.pdf).

O, many times have I seen the wave equation with periodic boundary
conditions:

$$\frac{1}{v^2}{\frac{\partial ^2}{\partial t^2}}\varphi(t,x) - {\frac{\partial ^2}{\partial x^2}}\varphi(t,x) = 0,$$

subject to $\varphi(t,0)=\varphi(t,L)$ for all $t$. Don’t we all just
**know** that the solutions are linear combinations of elements of the
form

$$e^{\pm i(k_n x \pm \omega_n t)},$$

with $$k_n = \frac{2\pi n}{L},\quad{n\in \mathbb{Z}},$$ and
$\omega_n = |k_n||v|$?

Don’t we all **knoooooooow** this?

Well I forgot how to do this and I should be doing other things but here
it goes.

What we all did sometime in the remote past
-------------------------------------------

Separate variables (of course!) by writing $\varphi(t,x)=f(x)g(t)$. Then
we have that $\partial_t\varphi(t,x) = f(x)g'(t)$ and
$\partial_x\varphi(t,x)=f'(x)g(t)$. Substitute that in:

$$\frac{1}{v^2}{\frac{\partial ^2}{\partial t^2}}\varphi(t,x) - {\frac{\partial ^2}{\partial x^2}}\varphi(t,x) =   \frac{1}{v^2}f(x)g''(t) - f''(x)g(t) .$$

Assume that $f(x)g(t)\neq 0$ and divide the right-hand side by
$f(x)g(t)$. Then we have

$$\frac{1}{v^2}\frac{1}{g(t)}g''(t) = \frac{1}{f(x)}f''(x).$$

Now fix
some value of $t$, say $t=0$. This equation implies that for all $x$

$$\frac{1}{f(x)}f''(x) = \frac{1}{v^2}\frac{1}{g(0)}g''(0) = \alpha,$$

where we have **defined** $\alpha$ as the right-hand side. It’s clearly
a constant. Similarly, if we fix an $x$, say $x=0$, we have that for
**all** $t$, the following equation holds:

$$\frac{1}{v^2}\frac{1}{g(t)}g''(t) = \frac{1}{f(0)}f''(0)=\alpha,$$

where the rightmost equality follows from the previous equation (which
holds for all $x$, in particular $x=0$). Then **both** terms are equal
to $\alpha$, a constant to be determined.

Let’s try to determine that. Let’s work on the equation for $f$. We have
that

$$f''(x) = \alpha f(x),$$

which we recognize as a simple
second-order homogeneous linear differential equation. The solutions to
this equation are of the form

$$f(x) = C_1e^{\mu x} + C_2e^{-\mu x},$$

where $C_1,C_2$ are constants to be determined and $\mu^2=\alpha$. Note
that $\mu$ might be complex, depending on whether $\alpha$ is positive
or negative (or complex too!). Now the periodic boundary conditions
imply $f(0)=f(L)$, so

$$f(0) = C_1+C_2 = C_1e^{\mu L } + C_2 e^{-\mu L} = f(L).$$

Save that for later. We also have that $f'(0) = f'(L)$, so

$$f'(0) = \mu C_1 - \mu C_2 = \mu C_1 e^{\mu L } - \mu C_2 e^{-\mu L}.$$

This implies that, assuming that $\mu\neq 0$,

$$C_1 - C_2 = C_1e^{\mu L} - C_2e^{-\mu L}.$$

Adding the conditions for $f(0)=f(L)$ and $f'(0)=f'(L)$ we obtain that $$C_1 = C_1 e^{\mu L},$$

which implies that either $C_1=0$ or $e^{\mu L}=1$. If the first case is
true then to avoid the trivial solution, we have to require $C_2\neq 0$
which implies $e^{-\mu L}=1$. Either way, this is unavoidable, and it
implies that $\mu L = 2\pi n i$ for some $n\in \mathbb{Z}$.

Therefore we can write

$$k_n = \frac{2\pi n}{L},\quad n\in \mathbb{Z},$$

so that $\mu = i k_n$ and the general solution to $f$ is

$$f(x) = C_1e^{ik_n x} + C_2 e^{-i k_n x}.$$

Nearly done. Now we work with the equation for $g$:

$$g''(t) = v^2\alpha g(t).$$

However, $\alpha = \mu^2 = (ik_n)^2=-k_n^2$, so the general solution is

$$g(t) = K_1e^{ik_n|v|t}+K_2e^{-i k_n |v|t}.$$

Here the constants $K_1,K_2$ are left unknown. Now we multiply $g(t)$ by $f(x)$:

$$\varphi(t,x) = f(x)g(t) = C_1K_1e^{i(k_n x + k_n|v|t)}+C_1K_2e^{i(k_n x - k_n|v|t)} + C_2K_1 e^{i(-k_n x + k_n|v|t)} + C_2K_2e^{i(-k_n x - k_n|v|t)}.$$

Now let $\omega_n = |k_n||v|$. Then the solution is a linear combination
of elements of the form

$$e^{\pm i (k_n x \pm \omega_n t)}.$$
