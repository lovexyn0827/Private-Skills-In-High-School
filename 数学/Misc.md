## 2024.4.6

$$
I(x)=e^x((x-1)e^x)-\frac43kx^3+kx,\forall k\in[1,2],x\in[0,k]\Rightarrow I_{max}
$$

解：$x\le\frac{\sqrt3}2$时，$I(x)\le e^{2x}(\frac{\sqrt3}2-1)-k(\frac43(\frac{\sqrt3}2)^3-\frac{\sqrt3}2)<0$

$x>\frac12$时，

$I'(x)=e^{2x}(2x-1)-k(4x^2-1)\\=(2x-1)(e^{2x}-k(4x-1))\\\ge(2x-1)(e^{2x}-8x+2)\\>(2x-1)(6-4\ln4)>0$

注意到$k=2$时，
$$
I(k)=I(2)=e^4-\frac{64}{3}+16>0
$$
故$I(x)$可能出现的最大值必然大于0，这在$x\in[0,\frac{\sqrt3}2]$时是不可能出现的，故这里只需考虑$\frac{\sqrt3}2<x\le k$的情形

前面已经证明，$I'(x)$在$x>\frac12$时恒大于0，故$(\frac{\sqrt3}2,k]$上$I(x)$必然单增，所以$I(x)\le I(k)=e^{2k}(k-1)-\frac43k^4+k^2$

此处设$f(k)=e^{2k}(k-1)-\frac43k^4+k^2$
$$
f'(k)=e^{2k}(2k-1)-\frac{16}3k^3+2k
$$

$$
f''(k)=4ke^{2k}-16k^2+2\ge4k(2ek)-16k^2+2=(8e-16)k^2+4k+2
$$

$1\le k\le2$时，$f''(k)>0$，$f'(k)\ge f'(1)=e^2-\frac{10}{3}>0$，$f(k)\le f(2)=e^4-\frac{64}3+16=e^4-\frac{16}{3}$。

综上，$I(x)\le f(x)\le e^4-\frac{16}3$，当且仅当$k=x=2$时诸等号成立。

> 有齐次特征的等式（如$a_n^2-(2n^2+2n)a_n+4n^3=0$，$e^{2x}-(2x+1)e^x+x^2+x=0$），尽可能尝试因式分解。（这个不算小众）
>
> > 所谓“齐次特征”，就是式中各项的次数可以认为是相同的。（只可意会，不可言传）如果一个表达式有齐次特征，那么我们便有可能使用类似于“十字相乘法”的因式分解方法对其进行分解。
> >
> > 比如这里，我们假设$e^{2x}-(2x+1)e^x+x^2+x$中形式比较“特别”的$e^x=t$，那么，那么那个式子就可以写成
> > $$
> > t^2-(2x+1)t+x^2+x=t^2-(2x+1)t+x(x+1)=(t-x)(t-x-1)
> > $$
> > 再举一例，对于$a_n^2-(2n^2+2n)a_n+4n^3=0$，我们设$t=a_n$，则它就可以被整理为
> > $$
> > t^2-(2n^2+2)t+4n^3=t^2-(2n^2+2)t+2n^2\cdot 2n=(t-2n^2)(t-2n)
> > $$

## 2024.5.31

特征根是指一类多项式方程的根，与微分方程、数列递推公式等有密切的联系。

(1) 假设$\{c_n\}$为一个等差数列，设$S_n$为数列$\left\{\frac{c_n}{2^n}\right\}$的前$n$项和，规定$S_0=0$，数列$\{d_n\}$由递推公式$d_{n+1}=2d_n+c_n$确定，$d_1=1$，求证：$d_n=2^n(AS_{n+B}+C)$，其中$A$、$B$、$C$均为与$c_n$无关的常数。

(2) 若代数式$\sum_{i=0}^na_ix_i=0$可以被通过移项变换为$\sum_{i=0}^{n-1}b_ix_{i+1}=\alpha\sum_{i=0}^{n-1}b_ix_i$，且$\alpha\ne0$，$a_n\ne0$，求证：

​	i. $\alpha$为关于$x$的方程$\sum_{i=0}^na_ix^i=0$的根

​	ii. 已知$\sum_{i=0}^na_ix^i=0$有$n$个根，则$\sum_{i=0}^{n-1}b_ix^i=0$根的集合为$\sum_{i=0}^na_ix^i=0$根的集合的子集。

(3) 已知数列$\{p_n\}$满足$p_{n+3}-3p_{n+1}-2p_n=0$，且$p_1=p_2=p_3=1$，求$\{p_n\}$的通项公式。

(1) 证明：不妨设$d_n=2^nD_n$，代入原递推方程
$$
2^{n+1}D_{n+1}=2^{n+1}D_n+c_n
$$
即
$$
D_{n+1}-D_n=\frac12\cdot\frac{c_n}{2^n}
$$
所以
$$
D_n=\frac12S_{n-1}+D_1=\frac12S_{n-1}+1
$$
所以
$$
d_n=2^n\left(\frac12S_{n-1}+1\right)
$$
所以$A=\frac12$，$B=-1$，$C=1$，均与$c_n$无关。

(2) 证明：i. 由$\sum_{i=0}^{n-1}b_ix_{i+1}=\alpha\sum_{i=0}^{n-1}b_ix_i$整理得
$$
\alpha b_0x_0-b_{n-1}x_n\sum_{i=1}^{n-1}(\alpha b_{i}-b_{i-1})x_{i}=0
$$
令上式与$\sum_{i=0}^na_ix_i=0$对应系数相等
$$
\alpha b_0=a_0
$$

$$
-b_{n-1}=a_n
$$

$$
\alpha b_{i}-b_{i-1}=a_i, (1\le i\le n-1)
$$

不妨设$b_i=\frac{t_i}{\alpha^i}$，代入上式
$$
\frac{t_i}{\alpha^{i-1}}-\frac{t_{i-1}}{\alpha^{i-1}}=a_i
$$
即
$$
t_i-t_{i-1}=a_i\alpha^{i-1}
$$
进而可得$1\le i\le n-1$时
$$
t_k=t_0+\sum_{i=1}^k a_i\alpha^{i-1}=\frac{a_0}{\alpha}+\sum_{i=1}^k a_i\alpha^{i-1}=\sum_{i=0}^k a_i\alpha^{i-1}
$$

$$
b_k=\alpha^{-k}\sum_{i=0}^k a_i\alpha^{i-1}
$$

考虑到
$$
b_{n-1}=\alpha^{1-n}\sum_{i=0}^{n-1} a_i\alpha^{i-1}=-a_0
$$
整理得
$$
\sum_{i=0}^n a_i\alpha^{i}=0
$$
原命题得证。

ii. 不妨设$\sum_{i=0}^na_ix^i=0$的$n$个根设为$x_1$、$x_2$、$\cdots$、$x_n$，则可将原方程整理为
$$
\sum_{i=0}^na_ix^i=a_n(x-x_1)(x-x_2)\cdots(x-x_n)=(x-x_1)(m_0+m_1x^1+m_2x^2+\cdots+m_{n-1}x^{n-1})=0
$$
即
$$
\sum_{i=1}^{n-1}m_ix^{i+1}=x_1\sum_{i=1}^{n-1}m_ix^{i}
$$
由i逆推可知$\alpha$可以是$\sum_{i=0}^na_ix^i=0$的任意实根，不妨取$\alpha=x_1$，则
$$
m_k=x_1^{-k}\sum_{i=1}^ka_ix_1^{i-1}=\alpha^{-k}\sum_{i=1}^ka_i\alpha^{i-1}=b_i
$$
所以
$$
\sum_{i=0}^{n-1}b_ix^i=\sum_{i=1}^{n - 1}m_ix^i=a_ix^i=a_n(x-x_2)\cdots(x-x_n)
$$
进而，$\sum_{i=0}^{n-1}b_ix^i=0$的根为$x_2$、$\cdots$、$x_n$，这些根也是$\sum_{i=0}^na_ix^i=0$的根，所以原结论成立。

(3) 解：参照
$$
p_{n+3}-3p_{n+1}-2p_n=0
$$
由(2)得，若方程$x^3-3x-2=0$可以被做因式分解$(x-r)(ax^2+bx+c)=0$，则上述递推公式可移项为
$$
ap_{n+3}+bp_{n+2}+cp_{n+1}=r(ap_{n+2}+bp_{n+1}+cp_{n})
$$
注意到-1是$x^3-3x-2=0$的一个根，则该方程可做以下因式分解
$$
(x+1)(x^2-x-2)=0
$$

$$
(x-2)(x^2+2x+1)=0
$$

继而可以将上述递推公式整理为
$$
p_{n+3}-p_{n+2}-2p_{n+1}=-(p_{n+2}-p_{n+1}-2p_{n})
$$

$$
p_{n+3}+2p_{n+2}+p_{n+1}=2(p_{n+2}+2p_{n+1}+p_{n})
$$

对第一种形式，设$q_n=p_{n+2}-p_{n+1}-2p_n$，由已知，$q_1=-2$，继而不难证明$\{q_n\}$为公比为-1的等比数列，可以写出
$$
q_n=p_{n+2}-p_{n+1}-2p_n=2(-1)^n
$$
同理
$$
p_{n+2}+2p_{n+1}+p_{n}=2^{n+1}
$$
解得
$$
p_{n+1}=-p_n+\frac23(2^n-(-1)^n)
$$
设
$$
p_n=(-1)^nr_n
$$
代入上式
$$
(-1)^{n+1}r_{n+1}=(-1)^{n+1}r_n+\frac23(2^n-(-1)^n)
$$

$$
r_{n+1}-r_n=-\frac23[(-2)^n-1]
$$

从而
$$
r_n=r_1+\frac23\sum_{i=1}^{n-1}[1-(-2)^n]=-1+\frac23[(n-1)+\frac{-2-(-2)^n}{3}]=\frac23n-\frac29(-2)^n-\frac{19}9
$$
进而
$$
p_n=(\frac23n-\frac{19}9)(-1)^n-\frac292^n
$$

# 2024.10.15

<img src="http://i0.hdslb.com/bfs/new_dyn/4262fad1510ae68803382728cced22271907393115.jpg" alt="img" style="zoom: 25%;" />

（1）解：由洛仑兹力作向心力
$$
m\frac{v_0^2}r=qvB
$$
由几何关系
$$
\sqrt3r\cdot \frac{\sqrt3}2=d
$$
解得
$$
v=\frac{3qBd}{2m}
$$
（2）【法一】解：由牛顿第二定律
$$
mv_x'=-qv_yB\tag{1}
$$

$$
mv_y'=qv_xB-qE\tag{2}
$$

对(2)两端同时求导
$$
mv_y''=qv_x'B
$$
联立(1)与上式有
$$
qv_yB=-mv_x'=-m\frac{m}{qB}v_y''
$$
即
$$
v_y''=-\frac{q^2B^2}{m^2}v_y
$$
解得
$$
v_y=v_r\sin\left(\frac{qB}m t+\varphi_0\right)
$$
继而
$$
v_x=\frac EB-v_r\cos\left(\frac{qB}m t+\varphi_0\right)
$$
考虑到初值条件，可解得
$$
v_r=\frac {\sqrt3E}B
$$

$$
\varphi_0=\frac\pi2
$$

所以
$$
v_y=\frac {\sqrt3E}B\cos\left(\frac{qB}mt\right)
$$

$$
y=\frac{\sqrt3mE}{qB^2}\sin\left(\frac{qB}m t\right)
$$

故粒子偏离$x$轴的最大距离为
$$
y_m=\frac{\sqrt3mE}{qB^2}
$$
【法二】解：由牛顿第二定律
$$
ma_x=-qv_yB
$$

$$
ma_y=qv_xB-qE
$$

设粒子相对一个以速度$\frac EB$水平向右匀速直线运动的参考系$R$的相对速度为$v_p$，相对加速度为$a_p$则
$$
v_x=v_p+\frac EB
$$

$$
a_p=v_p
$$

联立上述诸式有
$$
ma_p=-qBv_y
$$

$$
ma_y=qE+qBv_p-qE=qBv_p
$$

继而粒子相对参考系$R$的速度与加速度在坐标系中的斜率分别为
$$
k_1=\frac{v_y}{v_p}
$$

$$
k_2=\frac{a_y}{a_p}=-\frac{v_p}{v_y}
$$

所以$k_1k_2=-1$，加速度与速度垂直。而且
$$
\sqrt{a_p^2+a_y^2}=\frac{qB}{m}\sqrt{v_p^2+v_y^2}=\frac{qB}{m}v_r
$$
即相对加速度的大小与相对速度成正比。由上述分析知粒子相对$R$做匀速直线运动。

设粒子相对$R$做匀速圆周运动的线速度和半径分别为$v_r$、$r$，则有
$$
\sqrt{a_p^2+a_y^2}=\frac{qB}{m}\sqrt{v_p^2+v_y^2}=\frac{qB}{m}v_r=\frac{v_r^2}r\tag{1}
$$
初始状态下，易知
$$
v_{p0}=v_0\sin\frac\pi6-\frac EB=0
$$

$$
v_{y0}=v_0\cos\frac\pi6=\sqrt3\frac EB
$$

故粒子相对$P$做圆周运动的线速度
$$
v_{r}=\sqrt{v_{p0}^2+v_{y0}^2}=\frac{\sqrt3 E}B\tag{2}
$$
联立(1)(2)解得
$$
r=\frac{\sqrt 3mE}{qB^2}
$$
考虑到初态下粒子相对$R$的速度竖直向上，由几何关系，粒子等到达的最远位置
$$
y_m=r=\frac{\sqrt 3mE}{qB^2}
$$
【法三】解：假设粒子的速度由一个水平分量和一个符合匀速圆周运动的分量组成，且水平分量向右，大小为
$$
v_h=\frac EB
$$
假设粒子仅以线速度$v_r$做半径为$r$的圆周运动，则有
$$
m\frac{v_r^2}r=qv_rB
$$
假设粒子仅拥有$v_h$，则
$$
ma_y=qB\frac{E}B-qE=0
$$
物体







（3）【法一】解：由牛顿第二定律
$$
mv_x'=-kv_x-qv_yB\tag{1}
$$

$$
mv_y'=qv_xB-kv_y\tag{2}
$$

列出上述微分方程组的系数矩阵
$$
\boldsymbol A=\begin{pmatrix}
-\frac{k}{m}&-\frac{qB}{m}\\
\frac{qB}{m}&-\frac{k}{m}
\end{pmatrix}
$$
其特征值$\alpha$满足方程
$$
\alpha^2+\frac{2k}{m}\alpha+\frac{k^2}{m^2}=\left(\alpha+\frac km\right)=-\frac{q^2B^2}{m^2}
$$
解得
$$
\alpha=-\frac km\pm\frac{qB}{m}i
$$
故可给出$v_x'$形式如下
$$
v_x=C_1e^{\alpha_1t}+C_2e^{\alpha_2t}=Re^{-\frac kmt}\sin\left(\frac{qB}mt+\varphi\right)
$$

> 这一步的证明可以参考[前些天未完成的文稿](https://lovexyn0827.space/misc/docs/%E4%B8%80%E4%B8%AA%E5%AD%A6%E6%9C%9F%E8%A7%A3%E4%B8%80%E4%B8%AA%E6%96%B9%E7%A8%8B%E6%98%AF%E4%BB%80%E4%B9%88%E6%84%9F%E5%8F%97%EF%BC%88%E4%BA%8C%EF%BC%89.html)

回代入(1)解得
$$
v_y=-Re^{-\frac kmt}\cos\left(\frac{qB}mt+\varphi\right)
$$
结合初值条件解得
$$
R=-v_0
$$

$$
\varphi=-\theta
$$

解得
$$
v_x=v_0e^{-\frac kmt}\sin\left(\theta-\frac{qB}mt\right)
$$

$$
v_y=v_0e^{-\frac kmt}\cos\left(\theta-\frac{qB}mt\right)
$$

故
$$
y=\frac{kmv_0}{k^2+q^2B^2}\cos\theta-v_0e^{-\frac kmt}\left(\frac{qBm}{k^2+q^2B^2}\sin\left(\theta-\frac{qB}mt\right)+\frac{km}{k^2+q^2B^2}\cos\left(\theta-\frac{qB}mt\right)\right)
$$
令$v_y=0$，则可解得
$$
\cos\left(\theta-\frac{qB}mt\right)=0
$$

$$
\theta-\frac{qB}mt=-\frac\pi2
$$

$$
t=\frac{m}{qB}\left(\theta+\frac\pi2\right)
$$

此时$y$取最大值
$$
y_M=\frac{mv_0}{k^2+q^2B^2}\left(qBe^{-\frac{k}{qB}\left(\theta+\frac\pi2\right)}+k\cos\theta\right)
$$
由分析知$y_M$随$\theta$单调递减，故要使粒子可以尽可能地离开边界，$\theta$应取最小值0，此时
$$
y_M=\frac{mv_0}{k^2+q^2B^2}\left(qBe^{-\frac{\pi k}{2qB}}+k\right)
$$
令$y_M=d$，解得
$$
v_0=\frac{k^2+q^2B^2}{m\left(qBe^{-\frac{\pi k}{2qB}}+k\right)}d
$$
【法二】（超纲部分更少但依然不可避免，实际上应是永远不可避免）

解：由动量定理，若粒子恰好穿过磁场区域，竖直方向上
$$
0-mv_0\cos\theta=-k\overline{v_y}\Delta t+q\overline{v_x}B\Delta t
$$

$$
mv_{xT}-mv_0=-k\overline{v_x}\Delta t-q\overline{v_y}B\Delta t
$$

粒子轨迹方向上
$$
0-mv_0=-k\overline{v}\Delta t
$$
因为粒子在磁场中圆周运动的角速度与速度无关，故阻力造成的速度变化不影响粒子的运动时长。假定$k=0$，易知粒子在恰好能离开磁场区域时的运动时长为
$$
\Delta t=\frac{m}{qB}\left(\theta+\frac\pi2\right)
$$
这在$k\ne0$时同样成立。

由分析知，粒子向上直接入射，即$\theta=0$时，运动时长更短，全程中平均速率更大，故更容易穿过磁场区域，此时
$$
\Delta t=\frac{\pi m}{2qB}
$$

> 到这里必须引入一个超纲的结论，加速度与速度满足关系$a=-fv$的质点的$v-t$方程为$v=v_0e^{-ft}$，因为高中阶段的动量定理等工具只能研究边界状态，或特定中间状态中各量的联系（如单杆模型下速度与位移和时间的联系），而这里涉及了更一般的中间状态的求解。

由牛顿第二定律，粒子在轨迹方向上
$$
a=-\frac{k}{m}v
$$
故粒子离开磁场时的速度大小
$$
v_T=-v_{xT}=v_0e^{-\frac km \Delta t}=v_0e^{-\frac{\pi k}{2qB}}
$$
而
$$
\overline {v_y}\Delta t=d
$$
联立诸式解得
$$
v_0=\frac{k^2+q^2B^2}{m(qBe^{-\frac{\pi k}{2qB}}-k+qB)}d
$$






