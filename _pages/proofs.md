---
layout: page
permalink: /proofs/
title: proofs
description: Mathematical proofs and derivations.
nav: true
nav_order: 4
---

## Proofs

Below are selected mathematical proofs rendered with LaTeX.

---

### Problem 13 -- Taylor Series and Arcsin Function

**Problem.** Let

$$f(x) = x + \frac{2}{3} x^3 + \frac{2 \cdot 4}{3 \cdot 5} x^5 + \dots + \frac{2 \cdot 4 \dotsm 2n}{3 \cdot 5 \dotsm (2n + 1)} x^{2n + 1} + \dotsb$$

on the interval $$(-1,1)$$.

**(a)** Prove that $$(1 - x^2) f'(x) = 1 + xf(x).$$

**(b)** Prove that $$f(x) = \frac{\arcsin x}{\sqrt{1 - x^2}}.$$

**Solution.**

#### Part (a)

We let $$f(x)$$ be a Taylor Series on the interval $$(-1, 1)$$ by denoting

$$f(x)=\sum_{n=0}^{\infty}c_nx^{2n+1},$$

such that $$c_n=\frac{2\cdot4\cdot6\cdots2n}{3\cdot5\cdot7\cdots(2n+1)}$$. We take the derivative of our sum with respect to $$x$$, giving us

$$f'(x)=\sum_{n=0}^{\infty}c_n(2n+1)x^{2n}.$$

We then multiply both sides by $$(1-x^2)$$ to get

$$\begin{align*}(1-x^2)f'(x) &= (1-x^2)\sum_{n=0}^{\infty}c_n(2n+1)x^{2n}\\ &= \sum_{n=0}^{\infty}c_n(2n+1)x^{2n} - \sum_{n=0}^{\infty}c_n(2n+1)x^{2n+2}\\ &= \sum_{n=0}^{\infty}c_n(2n+1)x^{2n} - \sum_{n=1}^{\infty}c_{n-1}(2n-1)x^{2n}\\ &= c_0 + \sum_{n=1}^{\infty}[c_n(2n+1) - c_{n-1}(2n-1)]x^{2n}. \end{align*}$$

Now we simplify the coefficient of $$x^{2n}$$ for $$n \geq 1$$. After algebraic manipulation, we find that $$c_n(2n+1) - c_{n-1}(2n-1) = c_{n-1}$$.

Therefore,

$$\begin{align*}(1-x^2)f'(x) &= c_0 + \sum_{n=1}^{\infty}c_{n-1}x^{2n}\\ &= 1 + \sum_{k=0}^{\infty}c_kx^{2k+2}\\ &= 1 + x\sum_{k=0}^{\infty}c_kx^{2k+1}\\ &= 1 + xf(x). \end{align*}$$

#### Part (b)

Let $$g(x) = \sqrt{1 - x^2} f(x).$$ Then by the product rule:

$$\begin{align*}g'(x) &= \frac{d}{dx}[\sqrt{1 - x^2}] \cdot f(x) + \sqrt{1 - x^2} \cdot f'(x)\\ &= \frac{-x}{\sqrt{1 - x^2}} f(x) + \sqrt{1 - x^2} f'(x)\\ &= \frac{-xf(x) + (1-x^2)f'(x)}{\sqrt{1 - x^2}}\\ &= \frac{-xf(x) + 1 + xf(x)}{\sqrt{1 - x^2}}\\ &= \frac{1}{\sqrt{1 - x^2}}. \end{align*}$$

Since $$\frac{d}{dx}[\arcsin x] = \frac{1}{\sqrt{1-x^2}}$$, we have that $$g(x) = \arcsin x + C$$ for some constant $$C.$$

To find $$C$$, we evaluate at $$x = 0$$:

$$g(0) = \sqrt{1 - 0^2} f(0) = 1 \cdot f(0) = f(0) = 0.$$

Also, $$\arcsin(0) = 0$$, so $$g(0) = 0 + C$$, which gives us $$C = 0.$$

Therefore, $$g(x) = \arcsin x,$$ which means

$$\sqrt{1 - x^2} f(x) = \arcsin x,$$

so

$$f(x) = \frac{\arcsin x}{\sqrt{1 - x^2}}.\quad \blacksquare$$

---

### Series Convergence with Powers

**Theorem.** Let $$\{ a_n \}_{n=0}^{\infty}$$ be a sequence of positive real numbers. If $$\sum_{n=0}^{\infty} a_n$$ converges, then so does $$\sum_{n=0}^{\infty} {a_n}^r$$, where $$r$$ is a positive integer.

**Proof.** By the problem statement, we conclude that $$r \geq 1$$ since $$1$$ is the smallest positive integer.

We begin by considering

$$0< a_n\leq a_n^r \quad \forall a_n \geq 1$$

by the problem statement. However, we know that a sequence $$a_n$$ converges to zero if and only if

$$\exists \epsilon > 0 \text{ such that } |a_n-L|<\epsilon,$$

where we set $$L=0$$. When we set $$\epsilon=1$$, we see that $$0\leq a_k\leq 1$$ beginning at some point $$k$$ and continuing onwards for all $$n\geq k$$.

Since $$a_n\leq1$$ for all $$n\geq k$$, $$a_n^r$$ must also be less than or equal to $$1$$ for all $$n\geq k$$ since a positive real less than or equal to $$1$$ raised to a positive integer power will always be less than or equal to the original number before raising it to a power $$r$$.

Therefore, we can conclude that

$$\forall n \geq k, \quad 0 < a_n^r \leq a_n \leq 1.$$

Finally, by the Series Comparison Test, we know that $$\sum_{n=0}^{\infty} {a_n}^r$$ must converge since $$\sum_{n=0}^{\infty} a_n$$ also converges from the given condition and $$a_n^r\leq a_n$$ as $$n$$ approaches $$\infty$$. $$\quad \blacksquare$$

---

### Integral of Arctan

**Problem.** Compute $$\int \tan^{-1}x \,dx$$.

**Solution.** We must use integration by parts to solve this integral, but we notice that there are no obvious choices for $$dv$$ and $$u$$ since our integrand appears to consist of only one term. We set $$u=\tan^{-1}x$$ because we know $$\frac{d}{dx}\tan^{-1}x=\frac{1}{x^2+1}$$, forcing us to set $$dv=dx$$ since it is the only remaining term. We set $$du=\frac{1}{x^2+1}dx$$ and $$v=x$$ by the integral power rule.

Next, by integration by parts, we write

$$\int u\,dv=uv-\int v\,du \quad \rightarrow \quad \int\tan^{-1}x\,dx = x\tan^{-1}x-\int\frac{x}{x^2+1}dx.$$

We recognize that making a substitution will make our integral significantly easier to solve; we set $$x=\tan\theta$$ by substitution.

After our clever substitution, we have

$$\int\tan^{-1}x\, dx = \theta\tan\theta-\int\frac{\tan\theta}{\tan^2\theta+1} \sec^2\theta \,d\theta.$$

We may initially seem stuck, but we notice that when we divide our Fundamental Pythagorean Identity by $$\cos^2\theta$$, we get

$$\sin^2\theta+\cos^2\theta=1 \quad \rightarrow \quad \tan^2\theta + 1 = \sec^2\theta.$$

When we make this substitution using our trigonometric identity, we notice that our integrand simplifies nicely; our integral term can be written as

$$\int\frac{\tan\theta\sec^2\theta}{\sec^2\theta}d\theta=\int\tan\theta\,d\theta.$$

We will omit the proof for the antiderivative of tangent because we have proven it previously, but it's important to note that $$\int\tan\theta\,d\theta=\log\lvert\sec\theta\rvert+C$$ by substitution.

Combining this with our original equation, we have

$$\int\tan^{-1}x\, dx = \theta\tan\theta-\log\lvert\sec\theta\rvert +C.$$

We may think we're done, but we must remember that our original integral was written in terms of $$x$$, so our answer must also be in terms of $$x$$, not $$\theta$$. Fortunately, we can resolve this issue quickly.

We previously made the substitution $$x=\tan\theta$$. If we take the $$\arctan$$ of each side of the expression, we get $$\theta=\tan^{-1}x$$. Our final step is to rewrite our answer in terms of $$x$$:

$$\int\tan^{-1}x\, dx = x\tan^{-1}x-\log\lvert\sec(\tan^{-1}x)\rvert + C. \quad \blacksquare$$

---

### Orthogonal Curves

**Problem.** Find a set of curves that is orthogonal to the set $$\mathcal{F} = \{y = kx^2 : k \text{ is a constant}\}$$.

**Solution.** We let $$\mathcal{F}$$ and $$\mathcal{G}$$ denote a set of orthogonal curves, meaning that one or more of the curves in the sets intersect at a right angle.

We let $$\mathcal{F}=\{y=kx^2 :k \text{ is a constant}\}$$. Since $$k$$ is a constant that depends on the curves in $$\mathcal{F}$$, we want to express $$k$$ as a function of $$y$$ and $$x$$.

We rearrange $$y=kx^2$$ in terms of $$k$$, giving us

$$k=\frac{y}{x^2}.$$

Next, we take the derivative of $$y=kx^2$$, giving us

$$\frac{dy}{dx}=2kx$$

by implicit differentiation.

Next, we make our substitution for $$k$$, giving us

$$\frac{dy}{dx}=\frac{2y}{x}.$$

To find the orthogonal set, we take the negative reciprocal of our slope $$\frac{dy}{dx}$$:

$$\frac{dy}{dx}=-\frac{x}{2y}.$$

We solve this first-order differential equation by separation of variables:

$$\begin{align*}
2y\,dy&=-x\,dx \\
2\int y\,dy&=-\int x\,dx \\
y^2&=-\frac{1}{2}x^2+C \\
C&=y^2+\frac{1}{2}x^2 \\
C&=2y^2+x^2 \\
y&=\sqrt{\frac{C-x^2}{2}}
\end{align*}$$

for a variable constant $$C$$.

Therefore, because the set $$\mathcal{G} = \left\{y=\sqrt{\frac{C-x^2}{2}}\right\}$$ is orthogonal to $$\mathcal{F}$$ at a minimum of one point, we conclude that

$$\mathcal{G} = \left\{y=\sqrt{\frac{C-x^2}{2}}\right\}. \quad \blacksquare$$
