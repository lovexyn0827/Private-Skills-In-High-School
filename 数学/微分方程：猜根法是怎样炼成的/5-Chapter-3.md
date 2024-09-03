---
title: 三：高阶微分方程
date: false
keywords: 高中, 数学, 物理, 微分方程, 计算, lovexyn0827
desc: 高阶微分方程是指方程当中包含原函数的二阶及以上导数的微分方程，出现的最高导数阶数为n的方程为n阶微分方程，例如下面的方程即为一个二阶微分方程
id: differential_equation_high_school:5
draft: true
---

# 三：高阶微分方程

高阶微分方程是指方程当中包含原函数的二阶及以上导数的微分方程，出现的最高导数阶数为n的方程为n阶微分方程，例如下面的方程即为一个二阶微分方程
$$
f''(x)=f(x)\tag{3.1}
$$
不难猜出$f(x)=ae^x$为该方程的一个解（尽管不是全部）。

另外一个重要的特殊二阶微分方程是
$$
f''(x)=-\omega^2f(x)\tag{3.2}
$$
先看简化后的形式
$$
f''(x)=-f(x)\tag{3.3}
$$
尽管也不是那么明显，但是也可以联想到，$f''(x)=A\sin{x}$为该方程的解。

> 当初求解这一方程是为了验证简谐运动的运动方程，参考了结果的形式，所以便直接得出这样一个方程。

但是这很可能不会是原函数的唯一的一组解！

因为这里也是“导数=原函数×常数”的形式，我们尝试仿照最初的方法，将x替换为x的一次表达式
$$
f(x)=A\sin(kx+b)\tag{3.4}
$$
代入(3.2)有
$$
f''(x)=-k^2A\sin(kx+b)=-k^2f(x)=-\omega^2f(x)\tag{3.5}
$$
这样假定$k$、$\omega$均为非负数，便不难得出$k=\omega$，于是方程(3.2)的一组解为
$$
f(x)=A\sin{(\omega x+b)}\tag{3.6}
$$
这里来看一个应用：在劲度系数为$k$，弹性限度无限大的竖直弹簧上系有一质量为$m$的物块，重力加速度为常数$g$，物块由静止释放，求物块的$v-t$与$x-t$方程。

解：由牛顿第二定律
$$
ma=mv'=mx''=mg-kx\tag{3.7}
$$
对该方程两端同时求导，并整理得
$$
x'''=-\frac kmx'\tag{3.8}
$$
解得
$$
x'=v=v_m\sin{\left(\sqrt{\frac km}t+\phi\right)}\tag{3.9}
$$

$$
x=C-v_m\sqrt{\frac mk}\cos{\left(\sqrt{\frac km}t+\phi\right)}\tag{3.10}
$$

$$
a=x''=v_m\sqrt{\frac km}\cos{\left(\sqrt{\frac km}t+\phi\right)}\tag{3.11}
$$

考虑到$t=0$时，
$$
\begin{cases}
	a=x''=v_m\sqrt{\frac km}\cos{\left(\phi\right)}=g\\
	g=x'=v_m\sin{\left(\phi\right)}=0\\
	x=C-v_m\sqrt{\frac mk}\cos{\left(\phi\right)}=0
\end{cases}\tag{3.12}
$$
解得
$$
\begin{cases}
	\phi=0\\
	C=\frac{mg}k\\
	v_m=g\sqrt{\frac mk}
\end{cases}\tag{3.13}
$$
所以
$$
v=g\sqrt{\frac mk}\sin{\left(\sqrt{\frac km}t\right)}\tag{3.14}
$$

$$
x=\frac{mg}k\left[1-\cos{\left(\sqrt{\frac km}t\right)}\right]\tag{3.15}
$$

> 注意这里用到了一种在这可以算是比较重要的方法，即在求解形如$af(x)+bf'(x)+cf''(x)+\dots+d=g(x)$的方程时，可以考虑对方程两边同时求导消去常数项。类似地，对方程两边同求二阶导可以消去关于$x$的一次项，以此类推。

再看一种更一般的情况
$$
f''(x)+pf'(x)+qf(x)=0\tag{3.16}
$$
看到这种形式，我们可以联想到由二阶递推公式$a_{n+2}+pa_{n+1}+qa_n=0$求数列通项的题型。在那一题型当中，我们常常会尝试构造两个等比数列，再求解这两个等比数列通项公式确定的方程组得到答案：
$$
a_{n+2}+ma_{n+1}=k(a_{n+1}+ma_n)\tag{3.17}
$$

$$
\begin{cases}
	m-k=p\\
	-km=q
\end{cases}\tag{3.18}
$$

$$
\cases{
k=\frac{-p\pm \sqrt{p^2-4q}}{2}\\
m=\frac{p\pm\sqrt{p^2-4q}}{2}
}\tag{3.19}
$$

$$
\cases{
	a_{n+1}+m_1a_n=k_1^{n-1}(a_2+m_1a_1)\\
	a_{n+1}+m_2a_n=k_2^{n-1}(a_2+m_2a_1)
}\tag{3.20}
$$

$$
a_n=\frac{k_1^{n-1}(a_2+m_1a_1)-k_2^{n-1}(a_2+m_2a_1)}{m_1-m_2}\tag{3.21}
$$

这里求通项的一个关键是由构建的等比数列的递推式求出等比数列通项的过程$A_{n+1}=kA_n\Rightarrow A_n$，这一原理在微分方程当中也有所体现，即我们在前面已经得到的通过形如$F'(x)=kF(x)$的方程得到$F(x)$表达式的方法。接下来，我们来仿照求数列通项的过程求解方程(3.16)：

将方程整理为
$$
f''(x)+mf'(x)=k[f'(x)+mf(x)]\tag{3.22}
$$
其中$k$，$m$为常数。

则有
$$
f''(x)+(m-k)f'(x)-kmf(x)=0\tag{3.23}
$$
对应到原方程当中有
$$
\begin{cases}
	m-k=p\\
	-km=q
\end{cases}\tag{3.24}
$$
对方程组整理得
$$
\cases{
k^2-pk+q=0\\
m^2+pm+q=0
}\tag{3.25}
$$
解得
$$
\cases{
k_1=\frac{-p+\sqrt{p^2-4q}}{2}\\
m_1=\frac{p+\sqrt{p^2-4q}}{2}
}\tag{3.26}
$$
或
$$
\cases{
k_2=\frac{-p-\sqrt{p^2-4q}}{2}\\
m_2=\frac{p-\sqrt{p^2-4q}}{2}
}\tag{3.27}
$$
其中$k_1$、$k_2$分别为$k$在方程组(3.24)当中的取值，$m_1$、$m_2$分别为$m$在方程组(3.24)当中的取值

构建$F(x)=f'(x)+mf(x)$，则式(3.22)可写为
$$
F'(x)=kF(x)\tag{3.28}
$$
借助前面得到的公式(1.6)有，在$k$取$k_1$，$m$取$m_1$时有
$$
F(x)=f'(x)+m_1f(x)=A_1e^{k_1x}\tag{3.29}
$$
同时，取$f(x)$、$f'(x)$的共同定义域内一值$x_0$代入$F(x)$得到
$$
F(x_0)=f'(x_0)+m_1f(x_0)=A_1e^{k_1x_0}\tag{3.30}
$$
解得
$$
A_1=e^{-k_1x_0}[f'(x_0)+m_1f(x_0)]\tag{3.31}
$$
同理在$k$取$k_2$，$m$取$m_2$时有
$$
F(x)=f'(x)+m_2f(x)=A_2e^{k_2x}\tag{3.32}
$$

$$
A_2=e^{-k_2x_0}[f'(x_0)+m_2f(x_0)]\tag{3.33}
$$

联立(3.29)、(3.31)、(3.32)、(3.33)解得
$$
f(x)=\frac{[f'(x_0)+m_1f(x_0)]e^{k_1(x-x_0)}-[f'(x_0)+m_2f(x_0)]e^{k_2(x-x_0)}}{m_1-m_2}\tag{3.34}
$$

这就是我们所求的最终答案。

> 在高中时只研究了方程组(3.24)有两组不同实数解的情形，其他情形并未深入研究，这里再对它们进行补充。
>
> 若原方程只有一组解，则可以解得
> $$
> \cases{
> k=-\frac p2\\
> m=\frac p2
> }\tag{3.37}
> $$
>
> $$
> f'(x)+\frac p2f(x)=Ae^{-\frac p2x}\tag{3.38}
> $$
>
> 对上式整理，注意到
> $$
> A=e^{\frac p2x}[f'(x)+\frac p2f(x)]=[e^{\frac p2x}f(x)]'\tag{3.39}
> $$
> 所以
> $$
> Ax+C=e^{\frac p2x}f(x)\tag{3.40}
> $$
> 取$f(x)$、$f'(x)$定义域内两点$x_0$、$x_1$，有
> $$
> \cases{
> Ax_0+C=e^{\frac p2x_0}\\
> Ax_1+C=e^{\frac p2x_1}
> }\tag{3.41}
> $$
> 解得
> $$
> \cases{
> A=\frac{e^{\frac p2x_0}-e^{\frac p2x_1}}{x_0-x_1}\\
> C=\frac{x_1e^{\frac p2x_0}-x_0e^{\frac p2x_1}}{x_1-x0}
> }\tag{3.42}
> $$
> 所以
> $$
> f(x)=e^{\frac p2x}\left(\frac{e^{\frac p2x_0}-e^{\frac p2x_1}}{x_0-x_1}x+\frac{x_1e^{\frac p2x_0}-x_0e^{\frac p2x_1}}{x_1-x0}\right)\tag{3.43}
> $$
> 对于原方程组无实数解的情形，我们需要引入欧拉公式
> $$
> e^{ix}=\cos x+i\sin x\tag{3.44}
> $$
> 同时原方程组(3.24)的解为
> $$
> \cases{
> k_1=\frac{-p+i\sqrt{4q-p^2}}{2}\\
> m_1=\frac{p+i\sqrt{4q-p^2}}{2}
> }\tag{3.45}
> $$
> 或
> $$
> \cases{
> k_2=\frac{-p-i\sqrt{4q-p^2}}{2}\\
> m_2=\frac{p-i\sqrt{4q-p^2}}{2}
> }\tag{3.46}
> $$
> 其中$k_1$、$k_2$分别为$k$在方程组(3.24)当中的取值，$m_1$、$m_2$分别为$m$在方程组(3.24)当中的取值
>
> 代入式(3.34)有
> $$
> \begin{eqnarray}
> f(x)&=&\frac{[f'(x_0)+m_1f(x_0)]e^{\frac{-p+i\sqrt{4q-p^2}}{2}(x-x_0)}-[f'(x_0)+m_2f(x_0)]e^{\frac{-p-i\sqrt{4q-p^2}}{2}(x-x_0)}}{m_1-m_2}\\
> &=&\frac{[f'(x_0)+m_1f(x_0)]\left\{\cos{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}+i\sin{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}\right\}e^{-\frac{p}{2}(x-x_0)}-[f'(x_0)+m_2f(x_0)]\left\{\cos{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}-i\sin{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}\right\}e^{-\frac{p}{2}(x-x_0)}}{m_1-m_2}\\
> &=&\frac{2i\left[f'(x_0)+\frac p2f(x_0)\right]\sin{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}e^{-\frac{p}{2}(x-x_0)}-i\sqrt{4q-p^2}f(x_0)\cos{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}e^{-\frac{p}{2}(x-x_0)}}{2i\sqrt{4q-p^2}}\\
> &=&e^{-\frac{p}{2}(x-x_0)}\left\{\frac{\left[f'(x_0)+\frac p2f(x_0)\right]}{\sqrt{4q-p^2}}\sin{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}-\frac{f(x_0)}{2}\cos{\left[\frac{\sqrt{4q-p^2}}2(x-x_0)\right]}\right\}\\
> \end{eqnarray}\tag{3.47}
> $$
> 经整理可以得到$f(x)$的形式如下
> $$
> f(x)=ke^{ax}\sin{(\omega x+\phi)}\tag{3.48}
> $$
> 特殊地，前面的方程(3.2)可被视作方程(3.16)的一个特例：
> $$
> f''(x)+0\cdot f'(x)+\omega^2f(x)=0\tag{3.49}
> $$
> 代入前面得到的求解公式可得
> $$
> \begin{eqnarray}
> f(x)&=&\frac{f'(x_0)}{2\omega}\sin{\left[\omega(x-x_0)\right]}-\frac{f(x_0)}{2}\cos{\left[\omega(x-x_0)\right]}\\
> &=&\sqrt{\left[\frac{f'(x_0)}{2\omega}\right]^2+\left[\frac{f(x_0)}{2}\right]^2}\sin{\left[\omega(x-x_0)-\arctan{\frac{\omega f(x_0)}{f'(x_0)}}\right]}
> \end{eqnarray}\tag{3.50}
> $$
> 与先前我们得到的解的形式一致。