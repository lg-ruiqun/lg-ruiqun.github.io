## Lucas-Lehmer test

定理（Lucas 1878）：给定正素数 $p$，定义 $s_n$​ 为：

> Theorem (Lucas 1878): Given a positive prime $p$, define sequence $s_n$ as:

$$
\left\{\begin{aligned}s_0&=4\\s_n&=s_{n-1}^2-2\text{ for }n\geq1\end{aligned}\right.
$$

那么 $2^p-1$ 是素数当且仅当 $s_{p-2}\equiv0\pmod{2^p-1}$。

> Then $2^p-1$ is prime iff $s_{p-2}\equiv0\pmod{2^p-1}$.

证明：设 $\omega=2+\sqrt{3},\overline{\omega}=2-\sqrt{3}$。很显然，$s_n=\omega^{2^n}+\overline{\omega}^{2^n}$。这是因为

> Proof: Let $\omega=2+\sqrt{3},\overline{\omega}=2-\sqrt{3}$. Obviously, $s_n=\omega^{2^n}+\overline{\omega}^{2^n}$. This is because

$$
\begin{aligned}
s_0&=\omega^1+\overline{\omega}^1=4,\\
s_n&=s_{n-1}^2-2\\
&=(\omega^{2^{n-1}}+\overline{\omega}^{2^{n-1}})^2-2\\
&=\omega^{2^n}+\overline{\omega}^{2^n}+2(\omega\overline{\omega})^{2^{n-1}}-2\\
&=\omega^{2^n}+\overline{\omega}^{2^n}
\end{aligned}
$$

有了显示公式，我们就可以证明了。

> Now we've got the explicit formula. We can start our proof.

---

### 充分性 Sufficiency

我们现在有 $s_{p-2}\equiv0\pmod{2^p-1}$。这样必然存在一个整数 $k$，使得 $\omega^{2^{p-2}}+\overline{\omega}^{2^{p-2}}=k(2^p-1)$，所以 $\omega^{2^{p-2}}=k(2^p-1)-\overline{\omega}^{2^{p-2}}$。乘上 $\omega^{2^{p-2}}$ 可以得到 $\omega^{2^{p-1}}=k(2^p-1)\omega^{2^{p-2}}-1$。

> Now we have $s_{p-2}\equiv0\pmod{2^p-1}$. Then there must be an integer $k$ which satisfies $\omega^{2^{p-2}}+\overline{\omega}^{2^{p-2}}=k(2^p-1)$. Therefore $\omega^{2^{p-2}}=k(2^p-1)-\overline{\omega}^{2^{p-2}}$. Multiplying by $\omega^{2^{p-2}}$ gives $\omega^{2^{p-1}}=k(2^p-1)\omega^{2^{p-2}}-1$。

假设 $2^p-1$ 是合数，并且 $q$ 是 $2^p-1$ 的最小素因子，则 $q>2$。定义集合 $X=\{a+b\sqrt{3}\ |\ a,b\in\mathbb{Z}^+,0\leq a,b<q\}$。则可以对 $X$ 中的元素进行乘法（显然，结果仍然在 $X$ 内）。

> In a contradiction, if $2^p-1$ is composite and $q$ is the smallest prime factor of $2^p-1$, then $q>2$. Define a group $X=\{a+b\sqrt{3}\ |\ a,b\in\mathbb{Z}^*,0\leq a,b<q\}$. We can perform multiplications for elements in $X$ (Clearly, the result is still in $X$).

因为 $q>2$，$\omega$ 和 $\overline{\omega}$ 都在 $X$ 中。记 $X$ 中所有有逆元的元素构成的集合是 $X^*$，并且其大小是 $|X^*|\leq|X|-1=q^2-1$（因为 $0$ 没有逆元）。

> Because $q>2$，$\omega$ and $\overline{\omega}$ are both in $X$. The subset of elements in X with inverses forms a group $X^*$, with a size of $|X^*|\leq|X|-1=q^2-1$ ($0$ doesn't have a inverse).

现在 $2^p-1\equiv0\pmod q$ 且 $\omega\in X$，在 $X$ 中有 $k(2^p-1)\omega^{2^{p-2}}=0$。于是在 $X$ 中，$\omega^{2^{p-1}}=-1$，$\omega^{2^{p}}=1$。所以  $\omega\in X^*$，$\operatorname{ord}_X*\omega=2^p$，$|X^*|\geq2^p$。于是 $2^p\leq|X^*|\leq q^2-1<q^2\leq2^p-1<2^p$，矛盾。所以 $2^p-1$ 是素数。

> Now $2^p-1\equiv0\pmod q$ and $\omega\in X$, thus in $X$ we have $k(2^p-1)\omega^{2^{p-2}}=0$。Therefore in $X$, $\omega^{2^{p-1}}=-1$，$\omega^{2^{p}}=1$. Therefore  $\omega\in X^*$，$\operatorname{ord}_X*\omega=2^p$，$|X^*|\geq2^p$. From these we can get $2^p\leq|X^*|\leq q^2-1<q^2\leq2^p-1<2^p$. This yields the contradiction. So $2^p-1$ is prime.

---

### 必要性 Necessity

因为对于 $p>1$，$2^p-1\equiv3\pmod4$ 且 $2^p-1\equiv1\pmod3$，根据二次互反律，$(\frac{3}{2^p-1})=(\frac{1}{3})(-1)^\frac{(3-1)(2^p-2)}{4}=(-1)^{2^{p-1}-1}=-1$。也就是说 $3$ 是模 $2^p-1$ 意义下的非二次剩余。根据欧拉判别法，$3^{2^{p-1}-1}\equiv-1\pmod{2^p-1}$。

> Because for $p>1$, $2^p-1\equiv3\pmod4$ and $2^p-1\equiv1\pmod3$, according to the quadratic reciprocity law, $(\frac{3}{2^p-1})=(\frac{1}{3})(-1)^\frac{(3-1)(2^p-2)}{4}=(-1)^{2^{p-1}-1}=-1$. In other words, $3$ is a quadratic nonresidue modulo $2^p-1$. By Euler's criterion we can get $3^{2^{p-1}-1}\equiv-1\pmod{2^p-1}$.

作为对照，$2$ 是模 $2^p-1$ 意义下的二次剩余。根据欧拉判别法，有 $2^{2^{p-1}-1}\equiv1\pmod{2^p-1}$。将两个式子乘起来我们可以得到 $24^{2^{p-1}-1}\equiv-1\pmod{2^p-1}$。

> In a contrast, $2$ is a quadratic residue modulo $2^p-1$. According to the Euler's criterion, $2^{2^{p-1}-1}\equiv1\pmod{2^p-1}$. Combine the two equivalence relations we can get $24^{2^{p-1}-1}\equiv-1\pmod{2^p-1}$。

设 $\sigma=2\sqrt{3}$， $X=\{a+b\sqrt{3}\ |\ a,b\in\mathbb{Z}^*,0\leq a,b<2^p-1\}$。则在 $X$ 中，使用费马小定理和有限域中的二项式定理，有：

> Define $\sigma=2\sqrt{3}$ and $X=\{a+b\sqrt{3}\ |\ a,b\in\mathbb{Z}^*,0\leq a,b<2^p-1\}$. Then in $X$, by using the Fermat's little theorem and the Binomial Theorem in a finite field, there is:

$$
\begin{aligned}
(6+\sigma)^{2^p-1}&=6^{2^p-1}+2^{2^p-1}\times\sqrt{3}^{2^p-1}\\
&=6+(3^{2^{p-1}-1})\times2\sqrt{3}\\
&=6-2\sqrt{3}=6-\sigma
\end{aligned}
$$

然后我们发现 $\omega=\frac{(6+\sigma)^2}{24}$。于是有

> Then we discover $\omega=\frac{(6+\sigma)^2}{24}$. Then we get

$$
\begin{aligned}
\omega^{2^{p-1}}&=\frac{(6+\sigma)^{2^p}}{24^{2^{p-1}}}\\
&=\frac{(6+\sigma)(6+\sigma)^{2^p-1}}{24\times24^{2^{p-1}-1}}\\
&=\frac{(6+\sigma)(6-\sigma)}{-24}=-1
\end{aligned}
$$

最后就是把等式两边都乘上 $\overline{\omega}^{2^{p-2}}$ 并使用 $\omega\overline{\omega}=1$，我们可以得到

> All that remains is to multiply both sides of this equation by $\overline{\omega}^{2^{p-2}}$ and use $\omega\overline{\omega}=1$, which gives

$$
\begin{aligned}
\omega^{2^{p-1}}\overline{\omega}^{2^{p-2}}&=-\overline{\omega}^{2^{p-2}}\\
\omega^{2^{p-2}}+\overline{\omega}^{2^{p-2}}&=0\\
s_{p-2}&=0
\end{aligned}
$$

因为在 $X$ 中 $s_{p-2}$ 是零元，在模 $2^p-1$ 意义下也一定是零元。

> Since $s_{p-2}$ is $0$ in $X$, it's also $0$ modulo $2^p-1$.
