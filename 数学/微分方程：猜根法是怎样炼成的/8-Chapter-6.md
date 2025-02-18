---
title: 六：微分方程组
date: false
keywords: 高中, 数学, 物理, 微分方程, 计算, lovexyn0827
desc: 很多时候，我们研究的是多个变量相互作用的情况，这时，类似于我们常见的多元一次方程组，我们这里也需要列出多个微分方程来构成方程组，来看这样的一个例子：
id: differential_equation_high_school:8
draft: false
---

# 六：微分方程组

很多时候，我们研究的是多个变量相互作用的情况，这时，类似于我们常见的多元一次方程组，我们这里也需要列出多个微分方程来构成方程组，来看这样的一个例子：

## 加减消元法

水平面内的光滑平行直导轨上有两个金属杆A、B，质量分别为$m_1$、$m_2$，接入回路的电阻均为$r$，整个系统位于竖直向下的匀强磁场$B$当中，导轨间距为$L$。导轨的最左侧接有一定值电阻$R$，导轨足够长且电阻不计。开始时，$B$静止，$A$以$v_0$水平向右运动。描述杆A、B的运行过程。

解：由牛顿第二定律
$$
m_1a_A=m_1v_A'=-BI_AL\tag{6.1.1}
$$

$$
m_2a_B=m_2v_B'=-BI_BL\tag{6.1.2}
$$

由闭合电路欧姆定律
$$
I_A=\frac{BLv_A}{r+R}+\frac{BLv_A-BLv_B}{2r}\tag{6.1.3}
$$

$$
I_B=\frac{BLv_B}{r+R}+\frac{BLv_B-BLv_A}{2r}\tag{6.1.4}
$$

诸式联立有
$$
v_A'=-\left[\frac{B^2L^2}{m_1(R+r)}+\frac{B^2L^2}{2m_1r}\right]v_A+\frac{B^2L^2}{2m_1r}v_B\tag{6.1.5}
$$

$$
v_B'=-\left[\frac{B^2L^2}{m_2(R+r)}+\frac{B^2L^2}{2m_2r}\right]v_B+\frac{B^2L^2}{2m_2r}v_A\tag{6.1.6}
$$

……打住打住，我们直接接触的只是包含了一个函数的微分方程，而这里却是有两个函数要研究的耶！

联想到求解二元一次方程组时的“消元法”，我们可以尝试用一些技巧使上面关于两个函数的方程组变成关于一个函数的一个方程。这里不难发现，如果通过两式的加减，使得得到的新方程中关于$v_A$与$v_B$的成分的系数成比例，我们便可以获得一个$f'(x)=kf(x)$型的方程：

将式(6.1.6)乘以$n$加到(6.1.5)上，即求$(6.1.5)+n(6.1.6)$有
$$
v_A'+nv_B'=-B^2L^2\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n}{2m_2r}\right]v_A+B^2L^2\left[-\frac{n}{m_2(R+r)}+\frac{1}{2m_1r}-\frac{n}{2m_2r}\right]v_B\tag{6.1.7}
$$
令
$$
1:n=-\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n}{2m_2r}\right]:\left[-\frac{n}{m_2(R+r)}+\frac{1}{2m_1r}-\frac{n}{2m_2r}\right]\tag{6.1.8}
$$
即
$$
\frac{1}{2m_2r}n^2+\left(\frac{1}{2r}+\frac{1}{R+r}\right)\left(\frac1{m_2}-\frac{1}{m_1}\right)n-\frac{1}{2m_1r}=0\tag{6.1.9}
$$
式中
$$
\Delta=\left(\frac{1}{2r}+\frac{1}{R+r}\right)^2\left(\frac1{m_2}-\frac{1}{m_1}\right)^2+\frac1{m_1m_2r^2}>0\tag{6.1.10}
$$
可以设方程(6.1.9)的两个根分别为$n_1$、$n_2$，取(6.1.7)中$n$为$n_1$、$n_2$，结合式(6.8)分别有
$$
v_A'+n_1v_B'=-B^2L^2\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n_1}{2m_2r}\right]\left(v_A+n_1v_B\right)\tag{6.1.11}
$$

$$
v_A'+n_2v_B'=-B^2L^2\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n_2}{2m_2r}\right]\left(v_A+n_2v_B\right)\tag{6.1.12}
$$

上面两个方程均满足$f'(x)=kf(x)$的形式。为方便进一步表示，此处设
$$
k_1=-B^2L^2\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n_1}{2m_2r}\right]\tag{6.1.13}
$$

$$
k_2=-B^2L^2\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n_2}{2m_2r}\right]\tag{6.1.14}
$$

此时(6.1.11)、(6.1.12)的根分别可以被表示为
$$
v_A+n_1v_B=C_1e^{k_1t}\tag{6.1.15}
$$

$$
v_A+n_2v_B=C_2e^{k_2t}\tag{6.1.16}
$$

结合初始状态下A、B两杆的速度可知
$$
C_1=C_2=v_0\tag{6.1.17}
$$
此时
$$
v_A+n_1v_B=v_0e^{k_1t}\tag{6.1.18}
$$

$$
v_A+n_2v_B=v_0e^{k_2t}\tag{6.1.19}
$$

遂解得
$$
v_A=\frac{n_1e^{k_2t}-n_2e^{k_1t}}{n_1-n_2}\tag{6.1.20}
$$

$$
v_B=\frac{e^{k_1t}-e^{k_2t}}{n_1-n_2}v_0\tag{6.1.21}
$$

在(6.1.9)中，由韦达定理
$$
n_1+n_2=-2m_2r\left(\frac{1}{2r}+\frac{1}{R+r}\right)\left(\frac1{m_2}-\frac{1}{m_1}\right)\tag{6.1.22}
$$

$$
n_1n_2=-\frac{m_2}{m_1}<0\tag{6.1.23}
$$

$$
\begin{eqnarray}
k_1+k_2&=&-B^2L^2\left[\frac{2}{m_1(R+r)}+\frac{1}{m_1r}-\frac{n_1+n_2}{2m_2r}\right]\\
&=&-B^2L^2\left[\frac{2}{m_1(R+r)}+\frac{1}{m_1r}+\left(\frac{1}{2r}+\frac{1}{R+r}\right)\left(\frac1{m_2}-\frac{1}{m_1}\right)\right]\\
&=&-B^2L^2\left(\frac{1}{2r}+\frac{1}{R+r}\right)\left(\frac1{m_2}+\frac{1}{m_1}\right)<0\\
\end{eqnarray}\tag{6.1.24}
$$

$$
\begin{eqnarray}
k_1k_2&=&B^4L^4\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n_1}{2m_2r}\right]\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}-\frac{n_2}{2m_2r}\right]\\
&=&B^4L^4\left\{\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}\right]^2-\left[\frac{1}{m_1(R+r)}+\frac{1}{2m_1r}\right]\frac{n_1+n_2}{2m_2r}+\frac{n_1n_2}{4m_2^2r^2}\right\}\\
&=&B^4L^4\left[\frac{1}{m_1^2}\left(\frac{1}{R+r}+\frac{1}{2r}\right)^2+\left(\frac{1}{R+r}+\frac{1}{2r}\right)^2\left(\frac1{m_1m_2}-\frac{1}{m_1^2}\right)-\frac{1}{4m_1m_2r^2}\right]\\
&=&B^4L^4\left[\frac{1}{m_1m_2}\left(\frac{1}{R+r}+\frac{1}{2r}\right)^2-\frac{1}{4m_1m_2r^2}\right]\\
&=&\frac{B^2L^2}{m_1m_2(R+r)^2}+\frac{B^2L^2}{m_1m_2r(R+r)}>0
\end{eqnarray}\tag{6.1.25}
$$

所以$k_1$、$k_2$均小于0，$n_1$、$n_2$异号。不妨设$n_1<n_2$，有
$$
k_1<k_2<0\tag{6.1.26}
$$

$$
n_1<0<n_2\tag{6.1.27}
$$

对(6.1.20)、(6.1.21)两边同时求导有
$$
v_A'=\frac{n_2k_1e^{k_1t}-n_1k_2e^{k_2t}}{n_2-n_1}\tag{6.1.28}
$$

$$
v_B'=\frac{k_2e^{k_2t}-k_1e^{k_1t}}{n_2-n_1}\tag{6.1.29}
$$

若使$v_A'\ge0$，则有
$$
e^{k_2t-k_1t}\le\frac{n_2k_1}{n_1k_2}<0\tag{6.1.30}
$$
与$e^{k_2t-k_1t}>0$矛盾，故$v_A'<0$，$v_A$单调递减

考虑将$v_B'$写为
$$
v_B'=\frac{\frac{k_1}{k_2}-e^{(k_2-k_1)t}}{(n_2-n_1)k_2e^{k_1t}}\tag{6.1.31}
$$
在$t$分别小于、等于、大于$\frac{1}{k_2-k_1}\ln\frac{k_1}{k_2}>0$时，$v_B'$分别大于、等于、小于0，所以$v_B$先增大后减小。

考虑到$t\to+\infin$时，$v_A$、$v_B$均趋近于0，可知，过程当中，A杆从初速开始减速到趋于静止，B杆先从0开始加速，随后减速到趋于静止。

一般地，对于关于函数$f$、$g$的微分方程组
$$
\cases{
pf'+qg'=af+bg\\
rf'+sg'=cf+dg
}\tag{6.1.32}
$$
我们可以构建
$$
y=f+ng\tag{6.1.33}
$$
通过方程组中两方程的加减，调整含$f$，$g$的项系数的比例，使得$f$、$g$的系数之比与$f'$、$g'$的系数之比均为$n$，即在方程
$$
pf'+qg'+m(rf'+sg')=af+bg+m(cf+dg)\tag{6.1.34}
$$
即
$$
(p+mr)f'+(q+ms)g'=(a+mc)f+(b+md)g\tag{6.1.35}
$$
中
$$
p+mr:q+ms=a+mc:b+md=n\tag{6.1.36}
$$

$$
p+mr:a+mc=q+ms:b+md=k\tag{6.1.37}
$$

(6.1.36)与(6.1.37)可化为关于$m$、$n$或$k$的一元二次方程，验证其解可解的条件，分别设出（有时亦可直接解出）相应的其他参数，得到两个$y'=ky$形式的方程
$$
(f+n_1g)'=k_1(f+n_1g)\tag{6.1.38}
$$

$$
(f+n_2g)'=k_2(f+n_2g)\tag{6.1.39}
$$

(6.1.38)与(6.1.39)的解构成了一个关于$f$与$g$的二元一次方程组，由此得出$f$、$g$的解析式后，按题设对参数$n$、$k$的参数进行分析即可。

同时，我们也可以注意到，在很多时候，我们会自然地利用求导前后函数系数的一致性，也就是$[af(x)+bg(x)]'=af'(x)+bg'(x)$这一特性。

但是，上面的解题过程是针对化简后的二次方程的根均不是比例方程的增根的情形展开的，但如果二次方程有一个根恰好为增根（可以验证，两个根都是增根的情形实际上不需要联立即可求解），我们便不能够得出我们需要的关于目的函数的二元一次方程组，这时又该怎么办呢？再来一个与上边略微相似的例子：

水平面内的光滑平行直导轨上有两个金属杆A、B，质量分别为$m_1$、$m_2$，整个系统位于竖直向下的匀强磁场$B$当中，A、B、导轨构成的回路电阻视为定值$R$，导轨间距为$L$。开始时，$B$静止，$A$以$v_0$水平向右运动。描述杆B的运行过程。

解：由闭合电路欧姆定律
$$
BLv_A-BLv_B=IR\tag{6.1.40}
$$
由牛顿第二定律
$$
-BIL=m_1a_A\tag{6.1.41}
$$

$$
BIL=m_2a_B\tag{6.1.42}
$$

连立解得
$$
a_A=v_A'=\frac{B^2L^2}{m_1R}(v_B-v_A)\tag{6.1.43}
$$

$$
a_B=v_B'=\frac{B^2L^2}{m_2R}(v_A-v_B)\tag{6.1.44}
$$

$$
v_A'+nv_B'=\frac{B^2L^2}{R}\left[\left(\frac{n}{m_2}-\frac{1}{m_1}\right)v_A+\left(\frac{1}{m_1}-\frac{n}{m_2}\right)v_B\right]\tag{6.1.45}
$$

令方程(6.1.45)中关于$v_A$与$v_B$的成分成比例，即
$$
1:n=\left(\frac{n}{m_2}-\frac{1}{m_1}\right):\left(\frac{1}{m_1}-\frac{n}{m_2}\right)\tag{6.1.46}
$$

即
$$
\frac{n^2}{m_2}+\left(\frac{1}{m_2}-\frac{1}{m_1}\right)n-\frac1{m_1}=0\tag{6.1.47}
$$
解得$n=-1$或$n=\frac{m_2}{m_1}$，但是后者是增根。$n=-1$时有
$$
v_A'-v_B'=-\frac{B^2L^2}{R}\left(\frac1{m_1}+\frac1{m_2}\right)(v_A-v_B)\tag{6.1.48}
$$
此时方程满足形式$f(x)=kf(x)$，解得
$$
v_A-v_B=Ce^{-\frac{B^2L^2}{R}\left(\frac1{m_1}+\frac1{m_2}\right)t}\tag{6.1.49}
$$
$t=0$时有
$$
v_A=v_0\tag{6.1.50}
$$

$$
v_B=0\tag{6.1.51}
$$

此时可以解得
$$
C=v_0\tag{6.1.52}
$$

$$
v_A-v_B=v_0e^{-\frac{B^2L^2}{R}\left(\frac1{m_1}+\frac1{m_2}\right)t}\tag{6.1.53}
$$

同时，我们不妨尝试将增根$n=\frac{m_2}{m_1}$代入(6.1.45)，可得
$$
v_A'+\frac{m_2}{m_1}v_B'=0\tag{6.1.46}
$$
故$v_A+\frac{m_2}{m_1}v_B$为常数$(v_A+\frac{m_2}{m_1}v_B)|_{t=0}=v_0$，即
$$
v_A+\frac{m_2}{m_1}v_B=v_0\tag{6.1.47}
$$
与(6.1.53)连立解得
$$
v_B=\frac{m_1v_0}{m_1+m_2}\left[1-e^{-\frac{B^2L^2}{R}\left(\frac1{m_1}+\frac1{m_2}\right)t}\right]\tag{6.1.48}
$$
结合其他简单判定可以得出，B杆做加速度逐渐减小的匀加速运动，速度趋近于与$v_0$方向一致的一个定值。

在求解过程中，我们使用了比值式的增根。若想究其原因，先让我们来回想一下我们凑出那么一个比例关系的用意：我们的目的是构造一个由待求函数组成的新函数，用这个新函数及其导数替换下待求函数以实现消元；如果包含两个待求函数F、G本身系数的比例与其导数的系数的比例不同，则我们可以构造函数$H=aF+bG$，并用$H$进行换元将原函数成归我们熟悉的形式。如果我们遇到了增根，那么往往只是说明在代入增根后函数$H$中的$a$、$b$中在比例式中分母位置的那个值恰好为0，这时，我们可以通过加减两方程来完全抵消某一方程中含有某一待求函数的成分——我们甚至不用构造新函数。

当然，如果还能通过比如动量守恒等关系给出所求量的关系，加以利用还是会给计算带来很大的便利的。

## 代入消元法

水平面内的平面直角坐标系中，存在大小为$B$、竖直向上的匀强磁场，以及大小为$E$，沿$y$轴向下、大小为$E$的匀强电场。$t=0$时，有一质量为$m$、带电量$q$（$q>0$）的粒子P静止与原点，不计重力影响，描述P的运动轨迹

设P在$x$、$y$轴上的速度大小分别为$v_x$、$v_y$，加速度分别为$a_x$、$a_y$

由牛顿第二定律
$$
ma_x=mv_x'=qv_yB\tag{6.2.1}
$$

$$
ma_y=mv_y'=qE-qv_xB\tag{6.2.2}
$$

式(6.2.2)两边同时求导，有
$$
mv_y''=-qv_x'B\tag{6.2.3}
$$
联立(6.2.1)(6.2.3)有
$$
v_y''=-\frac{q^2B^2}{m^2}v_y\tag{6.2.4}
$$
注意到式(6.2.4)的形式与(3.2)相似，可以解得
$$
v_y=v_m\sin\left(\frac{qB}{m}t+\varphi\right)\tag{6.2.5}
$$
其中$v_m$与$\varphi$为常数。

(6.2.5)带入(6.2.2)有
$$
mv_y'=qE-qv_xB=qBv_m\cos\left(\frac{qB}{m}t+\varphi\right)\tag{6.2.6}
$$
解得
$$
v_x=\frac EB-v_m\cos\left(\frac{qB}{m}t+\varphi\right)\tag{6.2.7}
$$
考虑到$t=0$时有
$$
\begin{cases}
v_x=0
\\
v_y=0
\end{cases}\tag{6.2.8}
$$
代入(6.2.5)、(6.2.7)有
$$
\begin{cases}
0=\frac EB-v_m\cos\varphi\\
0=v_m\sin\varphi
\end{cases}\tag{6.2.9}
$$
即
$$
\cases{
\frac{E^2}{B^2}=v_m^2\cos^2\varphi\\
0=v_m^2\sin^2\varphi
}\tag{6.2.10}
$$
其中两式相加有
$$
\frac{E^2}{B^2}=v_m^2\tag{6.2.11}
$$
同时不难得到
$$
\varphi=\arcsin0=0\tag{6.2.12}
$$
最终解得
$$
v_x=\frac EB\left[1-\cos\left(\frac{qB}{m}t\right)\right]\tag{6.2.13}
$$

$$
v_y=\frac EB \sin\left(\frac{qB}{m}t\right)\tag{6.2.14}
$$

对上述两式两边同时积分解得P的坐标与时间的关系式
$$
x=\frac EB t-\frac{mE}{qB^2}\sin\left(\frac{qB}{m}t\right)+C_1\tag{6.2.15}
$$

$$
y=-\frac{mE}{qB^2}\cos\left(\frac{qB}{m}t\right)+C_2\tag{6.2.16}
$$

考虑到$t=0$时$x=y=0$，有
$$
\cases{
0=C_1\\
0=C_2-\frac{mE}{qB^2}
}\tag{6.2.17}
$$
解得
$$
x=\frac EB t-\frac{mE}{qB^2}\sin\left(\frac{qB}{m}t\right)\tag{6.2.18}
$$

$$
y=\frac{mE}{qB^2}\left[1-\cos\left(\frac{qB}{m}t\right)\right]\tag{6.2.19}
$$

注意到，以一个在直线$y=\frac{mE}{qB^2}$上沿$x$轴正方向以速度$\frac EB$运动的质点Q为参考系时，P相对Q的位置
$$
x_r=-\frac{mE}{qB^2}\sin\left(\frac{qB}{m}t\right)\tag{6.2.20}
$$

$$
y_r=-\frac{mE}{qB^2}\cos\left(\frac{qB}{m}t\right)\tag{6.2.21}
$$

且
$$
x_r^2+y_r^2=\left(\frac{mE}{qB^2}\right)^2\tag{6.2.22}
$$
即在参考系$Q$下，$P$绕$Q$做圆周运动。类似地可以证明P、Q的相对速度为定值，P在参考系Q下做匀速圆周运动

将P相对Q的运动叠加到Q的运动上，可得P相对原点参考系的运动模式，即匀速圆周运动与匀速直线运动的叠加。

> 这里可以来一道在高三上学期的某个周末硬凑的一道奇葩题目作为练习：
>
> 光滑水平面$xOy$内有一质量为$M$的小车$A$（视为质点），$A$上固定有一竖直光滑转轴， 轴上有一水平轻质刚性直竿$MN$在小车内部装置驱动下绕转轴上一点$P$在同一水平面内 以角速度$ω$逆时针匀速转动。杆两端 $M$、$N$ 分别固定质量为$m_1$、$m_2$的小球，$PN=l$，$PM=nl$。$t=0$时，小车静止于原点，$M$在$x$轴正半轴上。求小车坐标关于时间的关系式。

再来一例比较极端的：

我们知道，在两个反应
$$
A\longrightleftharpoons B\tag{6.2.23}
$$

$$
B\longrightleftharpoons C\tag{6.2.24}
$$

组成的恒容反应体系中，两者的平衡常数比较大时，$c(B)$会先增大，后减小到接近0。如果反应均视为基元反应，则反应速率均与反应物浓度成正比。两反应中正反应速率与反应物物质的量浓度的比例系数分别为$k_1$、$k_2$，逆反应忽略不计。初始状态下，体系内$c(A)=c_0$，试对反应体系中各物质的物质的量浓度变化规律进行建模，验证$c(B)$的最大值是否一直存在，并求解其具体表达式。

> 其实即使没学化学也不妨碍下面解方程。
>
> 记得这道题是在2022年12月想到的，在化学课上老师讲题的时候偷偷地就去做了。好像这道题也是那个我们用了好几遍的公式(4.13)的一个最初来源。

解：设$A$、$B$、$C$的物质的量浓度分别为$C_A$、$C_B$，由题意
$$
C_A'=-k_1C_A\tag{6.2.25}
$$

$$
C_B'=k_1C_A-k_2C_B\tag{6.2.26}
$$

由(6.2.25)结合系统初态不难解得
$$
C_A=c_0e^{-k_1t}\tag{6.2.27}
$$
进而
$$
C_B'=k_1c_0e^{-k_1t}-k_2C_B\tag{6.2.28}
$$
由公式(4.13)
$$
C_B=e^{-k_2t}\int k_1c_0e^{-k_1t}\cdot dt=-c_0e^{-(k_1+k_2)t}+Ce^{-k_2t}\tag{6.2.29}
$$
结合初态可知
$$
C_B=c_0\left[e^{-k_2t}-e^{-(k_1+k_2)t}\right]\tag{6.2.30}
$$

$$
C_B'=c_0(k_1+k_2)e^{-k_2t}\left[e^{-k_1t}-\frac{k_2}{k_1+k_2}\right]\tag{6.2.31}
$$

不难验证$C_B$总有极大值点
$$
t_0=\frac1{k_1}\ln\frac{k_1+k_2}{k_2}\tag{6.2.32}
$$
代入(6.2.30)
$$
C_{Bmax}=c_0\left[\left(\frac{k_1+k_2}{k_2}\right)^{-\frac{k_2}{k_1}}-\left(\frac{k_1+k_2}{k_2}\right)^{-\frac{k_1+k_2}{k_1}}\right]\tag{6.2.33}
$$
以上两类例子当中涉及的主要方法分别对应二元一次方程的“加减消元法”与“代入消元法”。但是，在使用“加减消元法”时，我们无法直接将含有任意一个函数的部分完全消去，因为这种操作下我们本质上是在求解关于两个函数及其导数的四元方程组，在只有两个方程可用时是无法完成的。而“代入消元法”当中，我们对方程组当中的一个方程两端同时进行了求导操作，这实际上利用了函数与其导数的关系，将含有同一函数的成分进行了一种“一体化”的操作。

但是，有时候，比如在求解包含非线性微分方程的方程组时，我们可能不能很方便地使用上述两类方法求解。这时，我们还有另一类求解方法。

## 主元法

有时，若方程组当中的一个方程包含多个函数，而且在将其中一个函数F视为主元时原方程可以方便地求解，我们还可以先将F解为一个含有其它函数表达式的形式，替换其它方程中出现的F，以实现消元。

现在考虑下面两个方程构成的方程组：
$$
f'(x)=g(x)f(x)\tag{6.3.1}
$$

$$
g'(x)=\ln f(x)\tag{6.3.2}
$$

利用公式(2.8)求解第一个方程有
$$
f(x)=ae^{\int g(x)\cdot dx}\tag{6.3.3}
$$
代入第二个方程
$$
g'(x)=\ln f(x)=\ln a+\int g(x)\cdot dx\tag{6.3.4}
$$
两边同时求导
$$
g''(x)=g(x)\tag{6.3.5}
$$
注意到
$$
g(x)=be^{\pm x}\tag{6.3.6}
$$
满足条件。进而解得
$$
f(x)=e^{\pm be^{\pm x}}\tag{6.3.7}
$$
至此求解完毕。

## 二元以上的方程组

还是来一个例子边算边讲：光滑水平面上现有质量均为$m$的三个物块A、B、C自右向左依次直线排列，AB、BC中间分别有劲度系数分别为$k_1$、$k_2$（$k_1\ne k_2$）的轻质长弹簧。初始时，弹簧处于原长，A的速度为$v_0$，B、C静止，求三者的$v-t$方程。

> 两个物块的情形留作练习。

解：设A、B、C发生的位移分别为$x_A$、$x_B$、$x_C$，由牛顿第二定律
$$
ma_A=mx_A''=-k_1(x_A-x_B)\tag{6.4.1}
$$

$$
ma_B=mx_B''=k_1(x_A-x_B)-k_2(x_B-x_C)\tag{6.4.2}
$$

$$
ma_C=mx_C''=-k_2(x_C-x_B)\tag{6.4.3}
$$

我们可以尝试使用与前边相似的“加减消元法”来解此方程组。三个方程两边分别乘以$p$、$q$、$r$，然后相加
$$
pmx_A''+qmx_B''+rmx_C''=\left(qk_1-pk_1\right)x_A+(pk_1-qk_1-qk_2+rk_2)x_B+(qk_2-rk_2)x_C\tag{6.4.4}
$$
令三个函数相应成分的系数成比例
$$
\frac{p}{qk_1-pk_1}=\frac{q}{pk_1-qk_1-qk_2+rk_2}=\frac{r}{qk_2-rk_2}\tag{6.4.5}
$$
即
$$
k_1p^2-k_1q^2-k_2pq+k_2pr=0\tag{6.4.6}
$$

$$
k_2r^2-k_2q^2-k_1qr+k_1pr=0\tag{6.4.7}
$$

这一方程的求解比较困难，但是如果令$q=1$，可由计算机计算得知该方程有三个解
$$
\begin{matrix}
\begin{cases}
p_1=1\\
r_1=1
\end{cases}
&

\begin{cases}
p_2=\frac{k_2-\sqrt{k_1^2-k_1k_2+k_2^2}}{k_1-k_2}\\
r_2=\frac{-k_1+\sqrt{k_1^2-k_1k_2+k_2^2}}{k_1-k_2}
\end{cases}
&

\begin{cases}
p_3=\frac{k_2+\sqrt{k_1^2-k_1k_2+k_2^2}}{k_1-k_2}\\
r_3=-\frac{k_1+\sqrt{k_1^2-k_1k_2+k_2^2}}{k_1-k_2}
\end{cases}
\end{matrix}\tag{6.4.8}
$$

> 其中第一个解实际上对应动量守恒式

分别回代到(6.4.4)
$$
mx_A''+mx_B''+mx_C''=0\tag{6.4.9}
$$

$$
p_2mx_A''+mx_B''+r_2mx_C''=(p_2k_1+r_2k_2-k_1-k_2)(p_2x_A+x_B+r_2x_C)\tag{6.4.10}
$$

$$
p_3mx_A''+mx_B''+r_3mx_C''=(p_3k_1+r_3k_2-k_1-k_2)(p_3x_A+x_B+r_3x_C)\tag{6.4.11}
$$

考虑初态后分别解得
$$
x_A+x_B+x_C=v_0t\tag{6.4.12}
$$

$$
p_2x_A+x_B+r_2x_C=p_2v_0e^{(p_3k_1+r_3k_2-k_1-k_2)t}\tag{6.4.13}
$$

$$
p_3x_A+x_B+r_3x_C=p_3v_0e^{(p_3k_1+r_3k_2-k_1-k_2)t}\tag{6.4.13}
$$

由此，我们一般可求解出$x_A$、$x_B$、$x_C$的表达式，求导后即得到相应的$v-t$方程。

由此可见，除非我们能事先地解出一部分函数的具体表达式或直接抵消一部分函数，一般的多元微分方程组的求解时相当复杂的。即使我们可以勉强地求出方程的解，后续的参数取值分析也会特别复杂。

> 有兴趣的话可以计算一下上文中“逆反应不计”的那一个例子在逆反应不可忽略时的情形，那也是特别复杂的，而且同样涉及我们所无法处理的三次方程。（自己就先不算了）
