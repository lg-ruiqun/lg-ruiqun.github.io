## Fibonacci and Lucas Sequence

斐波那契数列大家应该都熟悉吧。它的定义是这样的：

> Y'all should be familiar with the Fibonacci Sequence. It's definition is like below:

$$
F_n=\begin{cases}
0&(n=0)\\
1&(n=1)\\
F_{n-1}+F_{n-2}&(n\geq2)
\end{cases}
$$

其实斐波那契数列对于负数下标也是有定义的。

> Actually, it's also defined for negative indexes.

卢卡斯序列 $L_n$ 也是一个类似的序列，只不过 $L_0=-2,L_1=1$。

> Lucas sequence $L_n$ is a similar sequence, but $L_0=-2,L_1=1$.

它有如下的性质：

> They have these features:

1. $F_{n-1}+F_{n+1}=L_n$

   证明：使用数学归纳法。

   > Proof: Use the Mathematical Induction.

2. $F_{2n}=F_n^2+2F_nF_{n-1}$

   证明：右边等价于 $F_n(F_{n+1}+F_{n-1})$​。然后化简：

   > Proof: The right-hand side is equivalent to $F_n(F_{n+1}+F_{n-1})$. Then simplify:

   $$
   \begin{aligned}
   F_n^2+2F_nF_{n-1}&=F_n(F_{n+1}+F_{n-1})\\
   &=F_nL_n=F_{2n}
   \end{aligned}
   $$

3. 设 $\alpha=\frac{1+\sqrt5}2,\beta=\frac{1-\sqrt5}2$​，则

   > Let $\alpha=\frac{1+\sqrt5}2,\beta=\frac{1-\sqrt5}2$, then

   $$
   \begin{aligned}
   F_n&=\frac1{\sqrt5}(\alpha^n-\beta^n)\\
   L_n&=\alpha^n+\beta^n
   \end{aligned}
   $$

   证明：使用数学归纳法。

   > Proof: Use the Mathematical Induction.

4. $F_n=\sum_{i=0}^\infty\binom{n-i}i$

   证明：使用数学归纳法。

   > Proof: Use the Mathematical Induction.

   $$
   \begin{aligned}
   F_{n-1}+F_n&=\sum_{i=0}^\infty\binom{n-1-i}i+\sum_{i=0}^\infty\binom{n-i}i\\
   &=1+\sum_{i=1}^\infty\binom{n-i}{i-1}+\sum_{i=1}^\infty\binom{n-i}i\\
   &=1+\sum_{i=1}^\infty\binom{n+1-i}i\\
   &=\sum_{i=0}^\infty\binom{n+1-i}i=F_{n+1}
   \end{aligned}
   $$

5. ${\begin{pmatrix}F_{{n+2}}&F_{{n+1}}\\F_{{n+1}}&F_{{n}}\end{pmatrix}}={\begin{pmatrix}1&1\\1&0\end{pmatrix}}^{{n+1}}$

6. $\sum_{i=0}^nF_i=F_{n+2}-1$

7. $\sum_{i=1}^niF_i=nF_{{n+2}}-F_{{n+3}}+2$

8. $F_mF_{n-1}+F_{m-1}F_n=F_{m+n}$

9. $L_n^2=5F_n^2+4(-1)^{n}$

10. $F_n=\frac{L_{n-1}+L_{n+1}}5$

    证明：使用数学归纳法。

    > Proof: Use the Mathematical Induction.

    对于第八个结论，假定对于固定的 $m$，$n-1$ 和 $n-2$ 时结论都成立。则 $n$ 时

    > For the eighth conclusion, assume that for constant $m$ and $n-1$ and $n-2$ this formula is right. Then for $n$,

    
    $$
    \begin{aligned}
    F_mF_{n-1}+F_{m-1}F_n&=F_m(F_{n-2}+F_{n-3})+F_{m-1}(F_{n-1}+F_{n-2})\\
    &=F_mF_{n-3}+F_{m-1}F_{n-2}+F_mF_{n-2}+F_{m-1}F_{n-1}\\
    &=F_{m+n-2}+F_{m+n-1}=F_{m+n}
    \end{aligned}
    $$
    对于 $m$​ 同理。

    > The same for $m$.

11. $F_{n-(\frac{5}{n})}\equiv0\pmod n\Leftarrow n\in\mathbb P$

    证明：使用通项公式、二项式展开。

    > Proof: Use the explicit formula and the Binomial Theorem.

    1. 对于 $n\equiv\pm1\pmod5$，有 $(\frac 5n)=1$。根据欧拉判别法，$5^\frac{p-1}2\equiv1\pmod p$。

       > For $n\equiv\pm1\pmod5$, we have $(\frac 5n)=1$. According to Euler's criterion, $5^\frac{p-1}2\equiv1\pmod p$。

       $$
       \begin{matrix}
       F_p=\frac2{2^p\sqrt5}\left(\dbinom p1\sqrt5+\dbinom p3\sqrt5^3+\ldots+\dbinom pp\sqrt5^p\right)\equiv\sqrt5^{p-1}\equiv1\pmod p\\
       F_{p+1}=\frac2{2^{p+1}\sqrt{5}}\left(\dbinom{p+1}1\sqrt5+\dbinom{p+1}3\sqrt5^3+\ldots+\dbinom{p+1}p\sqrt5^p\right)\equiv\frac12\left(1+\sqrt5^{p-1}\right)\equiv1\pmod p\\
       F_{p-1}=F_{p+1}-F_p\equiv0\pmod p
       \end{matrix}
       $$

    2. 对于 $n\equiv\pm2\pmod5$，有 $(\frac5n)=-1$。根据欧拉判别法，$5^\frac{p-1}2\equiv-1\pmod p$​。

       > For $n\equiv\pm2\pmod5$, we have $(\frac 5n)=-1$. According to Euler's criterion, $5^\frac{p-1}2\equiv-1\pmod p$。

       $$
       F_{p+1}=\frac2{2^{p+1}\sqrt{5}}\left(\dbinom{p+1}1\sqrt5+\dbinom{p+1}3\sqrt5^3+\ldots+\dbinom{p+1}p\sqrt5^p\right)\equiv\frac12\left(1+\sqrt5^{p-1}\right)=\frac12(1+5^\frac{p-1}2)\equiv0\pmod p\\
       $$

    3. 对于 $n\equiv0\pmod5$，有 $n=5,F_5=5$。

       > For $n\equiv0\pmod5$, we have $n=5,F_5=5$.

12. 根据上面的等式，$F_n\bmod p$ 是有周期性的。

    > According to the equation before, $F_n\bmod p$ is periodic.
