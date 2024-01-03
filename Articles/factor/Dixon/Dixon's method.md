## Dixon's method

考虑 Fermat's Method：选取 $x$，计算 $n+x^2$。如果 $n+x^2=y^2$，且 $y$ 是一个整数，则 $n=(y+x)(y-x)$。这样就可以分解 $n$。

> Consider Fermat's Method: Choose $x$, compute $n+x^2$. If $n+x^2=y^2$ with $y$ an integer, then $n=(y+x)(y-x)$. This can factor $n$.

实际上就是要找一对整数 $(x,y)$，使得

> The idea is to find a pair of integers $(x,y)$ satisfying

$$
x^2\equiv y^2\pmod n
$$

然后我们建立一个_因子基_，并随机 $x$，计算 $m\equiv x^2\pmod n$，然后使用因子基分解 $m$，将这组关系式加入一个 01 矩阵之中。

> Then we build up a _factor base_, and randomly choose $x$, compute $m\equiv x^2\pmod n$. After that, we use the factor base to factor $m$ and add the relation into a 01-matrix.

最后就是一次 01 矩阵求逆（这个矩阵很稀疏：一行中 1 元素不超过 $\log_2 n$ 个），并将 $x$ 相乘，得到

> The last step is to do an invert of the 01-matrix (This matrix is quite sparse: There're no more than $\log_2n$ 1 elements in a row), and multiply $x$, we can get

$$
x^2\equiv\prod_{i=1}^lp_i^{2k_i}\equiv(\prod_{i=1}^lp_i^{k_i})^2\pmod n
$$

实际上这个算法的时间复杂度是 $O(\exp((2+o(1))\sqrt{\ln n\ln\ln n}))$。

> The actual time complexity of this algorithm is $O(\exp((2+o(1))\sqrt{\ln n\ln\ln n}))$.

---

我们可以使用_大素数_：$m$ 不一定是很好分解的数，所以我们可以使用大的素数来加速（但是不直接加入 01 矩阵），并在找到 $m$ 带两个同样大素数的关系式（称为“部分关系式”）时合并成可以加入因子基的关系式（称为“全关系式”）。

> We can use _large primes_: $m$ isn't always easy to factor, so we use large primes to accelerate the speed. When we find two relations (called "partial relation") which contain the same large prime, we combine them into a relation that can be added into the factor base (called "full relation").

举例：分解 $197209$。我们可以得到：

> For example: Factorize $197209$. We can get:

$$
\begin{aligned}
189428^2&\equiv2\times3\times7\times19\pmod{197209}\\
5926^2&\equiv2\times3^2\times13\times61\pmod{197209}\\
90522^2&\equiv5^2\times59\pmod{197209}\\
81227^2&\equiv5^2\times7^2\pmod{197209}\\
\end{aligned}
$$

从最后一个式子我们得到 $81227^2\equiv35^2\pmod{197209}$。所以我们做 $\gcd(81227-35,197209)=199$ 和 $\gcd(81227+35,197209)=991$。

> From the last equation we know $81227^2\equiv35^2\pmod{197209}$. So we perform $\gcd(81227-35,197209)=199$ and $\gcd(81227+35,197209)=991$.

（其实，在实际生活中我们不会这么幸运，所以通常需要解一个很大的矩阵。）

> (Actually, in real life we won't be such lucky, so we usually need to solve a large matrix.)