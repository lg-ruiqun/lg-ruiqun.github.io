## Legendre Symbol

如果一个整数在模 $p$ 意义下同余于一个完全平方数，则这个数是模 $p$ 意义下的二次剩余，反之亦然。勒让德符号是一个模素数的意义下判断一个数是否为二次剩余的工具。如果 $a$ 是模 $p$ 意义下的二次剩余，则 $(\frac{a}{p})=1$；如果 $a$ 是模 $p$ 意义下的非二次剩余，则 $(\frac{a}{p})=-1$；**如果 $a\bmod p=0$，则 $(\frac{a}{p})=0$。**

> An integer $a$ is a quadratic residue modulo $p$ if it is congruent to a perfect square modulo $p$ and is a quadratic nonresidue modulo $p$ otherwise. Legendre Symbol is a tool for telling whether a number is a quadratic residue modulo a prime. If $a$ is a quadratic residue modulo $p$, then $(\frac{a}{p})=1$; If $a$ is a quadratic nonresidue modulo $p$, then $(\frac{a}{p})=-1$; **If $a\bmod p=0$, then $(\frac{a}{p})=0$.**

勒让德符号有这些性质：

> Legendre Symbols have these features:

1. 完全积性（completely multiplicative）。

   即 $(\frac{a}{p})(\frac{b}{p})=(\frac{ab}{p})$。

2. 周期性（periodic）($\bmod p$)。

   若 $a\equiv b\pmod p$，则 $(\frac{a}{p})=(\frac{b}{p})$。

   > If $a\equiv b\pmod p$, then $(\frac{a}{p})=(\frac{b}{p})$.

还有一个关于勒让德符号的定理（欧拉判别法）。这个定理是：

> There's a theorem about Legendre Symbol (Euler's criterion). This theorem is:

$$
(\frac{a}{p})\equiv a^\frac{p-1}{2}\pmod p
$$

证明：设 $g$ 是一个模 $p$ 意义下的原根。注意到 $g$ 不是模 $p$ 意义下的二次剩余，因为如果 $g\equiv x^2\pmod p$，则 $\operatorname{ord}_pg\leq\frac{p-1}{2}$，与其定义矛盾。根据勒让德符号的完全积性和周期性，$g^a$ 为模 $p$ 意义下的二次剩余当且仅当 $a\equiv0\pmod2$。

> Proof: Let $g$ a generator modulo $p$. Notice that $g$ is a quadratic nonresidue modulo $p$. That's because if $g\equiv x^2\pmod p$, then $\operatorname{ord}_pg\leq\frac{p-1}{2}$, which yields the definition of $g$. By the completely multiplicative and the periodic features of Legrende Symbols, $g^a$ is a quadratic residue modulo $p$ iff $a\equiv0\pmod2$.

设 $i$ 是一个满足 $g^i\equiv a\pmod p$ 的整数，则

> Define $i$ an integer which satisfies $g^i\equiv a\pmod p$, thus

$$
\begin{aligned}
(\frac ap)&\equiv(\frac{g^i}p)\\
&\equiv(-1)^i\\
&\equiv g^{\frac{p-1}2\times i}\\
&=(g^i)^\frac{p-1}2\\
&\equiv a^\frac{p-1}2\pmod p
\end{aligned}
$$
