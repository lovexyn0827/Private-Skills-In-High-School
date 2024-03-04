# 负一：预备知识（积分）

这里的知识要求很简单：

- 高中数学知识
- 高中物理知识（其实不大会也没关系啦）
- 速度是位移对时间的导数，加速度是速度对时间的导数等
- 基础的不定积分计算方法

因为本文是面向高中生而写的，故此处我们简要的提一下“积分”的概念与一些重要方法。

减法是加法的逆运算，除法是乘法的逆运算，对数是指数的逆运算，类似地，积分是求导的逆运算，即，积分是在已知某函数导数的情况下求解原函数的一种运算。

来看下面的式子：
$$
f'(x)=2x\tag{-1.1}
$$
我们很容易就能注意到，$f(x)=x^2$时，上面的式子成立。也有细心的读者会发现，当$f(x)=x^2+C$（C为任意常数）时，上式亦成立。故我们记$2x$的不定积分为$x^2+C$，写作
$$
\int 2x\cdot dx=x^2+C\tag{-1.2}
$$
（其实不至于混淆的话那一个点也是可以省略的，这里写上只是笔者习惯）

看懂了吗？先来做几道练习吧！

1. $\int 2\cdot dx$
2. $\int x^2\cdot dx$
3. $\int \frac 1x\cdot dx$
4. $\int \sin{2x}\cdot dx$
5. $\int \ln{x}\cdot dx$
6. $\int (x^2+1)e^x\cdot dx$

emmm……应该前三四道大概还是简单的，但是，后面的题目或许就不是那种可以一眼秒掉的样子了。所以，因为积分这一操作相当重要，这里我们还是要讲一些基础的积分方法的。

来看这些积分

1. $\int e^x+x\cdot dx$
2. $\int x^2-2x+1\cdot dx$

再试着猜一下结果，有没有发现什么规律呢？

没错！一般地我们有：
$$
\int f(x)\pm g(x)\cdot dx=\int f(x)\cdot dx\pm\int g(x)\cdot dx\tag{-1.3}
$$
也就是说，先积分再加减和先加减再积分的结果是一样的。哦，和求导的规则一样耶！

还有一条
$$
\int af(x)\cdot dx=a\int f(x)\cdot dx\tag{-1,4}
$$
学会了吗？自己出几道题小试一下吧！

当然，和导数一样，我们不可以像下面这么计算
$$
\int f(x)g(x)\cdot dx=\left[\int f(x)\cdot dx\right]\cdot\left[\int g(x)\cdot dx\right]（错误示范）\tag{-1.5}
$$
实际上，两个函数积与商的积分是没有通用的运算法则的。类似地，复合函数的积分也很少能总结出通用的计算方法。

但是，我们还有三个强大的工具：积分表、换元积分与分部积分法。

积分表给出了一系列常见函数与其不定积分的对应关系。就高等数学教程给出的内容来说，积分表中给出了24个基本积分公式，这些公式的推导往往可能较为繁琐，地位相当于化学当中的元素周期表；此外，积分表中也给出了100余个常用积分公式，类比到化学当中就类似于各种常见的反应方程式。这里给出最常用的几个积分公式：
$$
\int x^{\alpha}\cdot dx=\frac{1}{\alpha+1}x^{\alpha+1}+C~~~(\alpha\ne-1)\tag{-1.6}
$$

$$
\int \frac1x\cdot dx=\ln|x|+C\tag{-1.7}
$$

$$
\int a^x\cdot dx=\frac{a^x}{\ln a}+C\tag{-1.8}
$$

$$
\int \sin{x}\cdot dx=-\cos{x}+C\tag{-1.9}
$$

$$
\int\cos{x}\cdot dx=\sin x+C\tag{-1.10}
$$

$$
\int 0\cdot dx=C\tag{-1.11}
$$

$$
\int a\cdot dx=ax\tag{-1.12}
$$

其他积分公式因为使用较少，此处暂不列出。（当然，如果能记住高数中24个常用积分，尤其是带$a^2\pm x^2$或$\sin^2x$的那种还是挺好的啦）

换元积分有两类，一类是用另一个“元（或者说字母）”来换下来一个含有自变量的一个表达式（比如用$t$换下来$\sin x$），也就是“用小的换下来大的”；另一类是用一个关于另一个“元（或者说字母）”的表达式替换掉自变量（比如用$\cos t$换下来$x$），也就是“用大的换下来小的”。先看应用最多的第一类换元法：

在求积分时，我们不妨设
$$
\int f(x)\cdot dx=g(h(x))+C\tag{-1.13}
$$
考虑到积分是求导的逆运算，而上边等式两边都是同一个函数（至少对应关系相同），我们对上式两边同时求导有
$$
f(x)=h'(x)g'(h(x))\tag{-1.14}
$$
这样，我们就得到了积分公式
$$
\int h'(x)g'(h(x))\cdot dx=\int g'(h(x))\cdot d(h(x))\xlongequal{t=h(x)}\int g'(t)\cdot dt=g(t)+C=g(h(x))+C\tag{-1.15}
$$
或许这样看起来有点懵圈？那先来一个具体的例子看一看：
$$
\int \sin(8x)\cdot dx=\frac18\int 8\sin{8x}\cdot dx=\frac18\int(8x)'\sin(8x)\cdot dx=\frac18\int \sin(8x)\cdot d(8x)=-\frac18\cos(8x)+C\tag{-1.16}
$$
可能这样看还是会有两个疑点：第一，$\int \sin(8x)\cdot d(8x)=-\cos(8x)+C$，最后的结果不应该是上面的式子乘以八分之一，等于$-\frac18\cos(8x)+\frac18C$吗；第二，$dx$我懂，$d(8x)$是个什么鬼？

先来看第一个，不定积分结果尾部补上一个常数$C$只是为了强调这样一个常数$C$是可以存在的，而不关注$C$的值究竟是多少。所以，此处$C$的系数无关紧要。甚至有时我们经一顿操作后不小心把最初的$C$变成了$e^C-e^{-C}$，我们再计算到最后把这一个整体都给再换成$C$也是可以的（尽管自己还是喜欢用$C_0$以示区分）。

再看第二个。讲到这里，我们还是避不开要讨论一下$d(\cdots)$究竟是什么的。一个视角是，放到不定积分里面，计算$\int balabala\cdot d(palapala)$就是吧$balabala$当成一个关于$palapala$的函数去求积分。比如计算$\int(e^t+t)^2\cdot d(e^t+t)$时，我们只需要计算$x^2$的积分$\frac13x^3+C$，再把$x=e^t+t$它代入到$\frac13x^3+C$当中，最终得出的结果就是$\frac13(e^t+t)^{3}+C$。另一个视角涉及导数的另一种表示，即$y$关于$x$的导数也可被记为$\frac{dy}{dx}$，再来看$\int balabala\cdot d(palapala)$，假设$balabala$也是$x$的一个函数，那么这样一个不定积分也可以被写作$\int balabala\cdot d(palapala)=\int balabala\frac{d(palapala)}{dx}\cdot dx=\int balabala(palapala)'\cdot dx$。咦，还能这么玩？不得不说，在不接触微分的情况下，这一点确实有点反直觉。

从$d(\cdots)$与导数表示的角度我们可能也会注意到，$d(\cdots)$这个操作和求导有一定的相似之处，其实，我们有
$$
d(f(x))=f'(x)\cdot dx\tag{-1.17}
$$
这样我们顺便也可以得到两个有用的公式
$$
\begin{eqnarray}
\int f(ax+b)\cdot dx&=&\frac1a\int af(ax+b)\cdot dx\\
&=&\frac1a\int(ax+b)'f(ax+b)\cdot dx\\
&=&\frac 1a\int f(ax+b)\cdot d(ax+b)\\
&=&\frac1af(ax+b)+C
\end{eqnarray}\tag{-1.18}
$$

$$
\int f(x)\cdot d(g(x))=\int f(x)(g(x))'\cdot dx=\int f(x)(g(x)+b)'\cdot dx=\int f(x)\cdot d(g(x)+b)\tag{-1.19}
$$

第二个公式告诉我们，在计算积分时$d$后边部分中可以被随意地加减一个常数，以使其与前边的部分相适应。

第二类换元法看起来简单，但是技巧性却特别强，这里篇幅有限，只给出一个典型的例子：
$$
\begin{eqnarray}
\int \sqrt{1-x^2}\cdot dx&\xlongequal{x=\sin t,t\in[-\frac\pi2,\frac\pi2]}&\int\sqrt{1-\sin^2 t}\cdot d(\sin t)\\
&=&\int\cos t(\sin t)'\cdot dt\\
&=&\int\cos^2 t\cdot dt\\
&=&\int\frac{1+\cos(2t)}{2}\cdot dt\\
&=&\frac12t+\frac14\int2\cos(2t)\cdot dt\\
&=&\frac12t+\frac14\sin(2t)+C\\
&=&\frac12t+\frac12\sin t\sqrt{1-\sin^2t}+C\\
&\xlongequal{x=\arcsin t}&\frac12\arcsin t+\frac12x\sqrt{1-x^2}+C
\end{eqnarray}\tag{-1.20}
$$
其中$\arcsin x$为$\sin{x}~~(x\in[-\frac\pi2,\frac\pi2])$的反函数。（由此可见，有些积分的结果是真的轻易猜不到的。）

实际上，第二类换元法下我们常用的换元方法就只有三角换元和双曲换元两种。

顺带再写一个不清楚要分到哪一类的换元积分：
$$
\int x\sqrt{1-x}\cdot dx\xlongequal{\matrix{t=\sqrt{1-x}\\x=1-t^2}}\int(1-t^2)t\cdot dt=\int t-t^3\cdot dt=\frac12t^2-\frac14t^4+C=-x^2+x+C\tag{-1.21}
$$
我们再看一下分部积分法：

先放公式
$$
\int{u\cdot dv}=uv-\int v\cdot du\tag{-1.22}
$$
或者说
$$
\int v'u\cdot dx=uv-\int u'v\cdot dx\tag{-1.24}
$$
其中$u$、$v$均为自变量$x$的函数。

> 可以发现，我们对式(-1.24)两端同时关于$x$求导后，经过整理可得函数积的导数公式；反之，函数积的导数公式也可推导上式。

乍看起来大概会让人一头雾水。这有什么用处呢？在这里我们尝试解一下前面遗留的两道题目：
$$
\int \ln x\cdot dx=\int(x)'\ln x\cdot dx=x\ln x-\int (\ln x)'x\cdot dx=x\ln x-\int 1\cdot dx=x\ln x-x+C\tag{-1.25}
$$

$$
\begin{eqnarray}
\int (x^2+1)e^x\cdot dx&=&\int (e^x)'(x^2+1)\cdot dx\\
&=&e^x(x^2+1)-\int2xe^x\cdot dx\\
&=&e^x(x^2+1)-\int(e^x)'2x\cdot dx\\
&=&e^x(x^2+1)-e^x2x+\int2e^x\cdot dx\\
&=&e^x(x^2-2x+3)+C
\end{eqnarray}\tag{-1.26}
$$

事实上，分部积分法要远比我们想象的要强大，很多多项式乘以其他函数或是$e^x$乘以其他函数形式的积分都可以通过分部积分法计算。就多项式的情形来说，分部积分法提供了“降次”与“升次”两种功能，其中降次最为常用：
$$
\int x\cos x\cdot dx=\int(\sin x)'x\cdot dx=x\sin x-\int \sin{x}\cdot dx=x\sin x+\cos x+C\tag{-1.27}
$$
还有两点需要说明。第一，不是所有函数都是有初等形式的原函数的（即不能用指、对、幂、三角、反三角、常数函数的有限次四则运算与复合表示），下面是两个典型的例子：
$$
\int e^{-x^2}\cdot dx\tag{-1.28}
$$

$$
\int\frac{e^x}{x}\cdot dx\tag{-1.29}
$$

（曾经被这两个积分坑过）

第二，计算积分时，要善用被积函数的等价变形，尤其是裂项一类操作：
$$
\int\frac{2}{x^2-1}\cdot dx=\int\frac{dx}{x-1}-\int\frac{dx}{x+1}=\ln\left|\frac{x-1}{x+1}\right|+C\tag{-1.30}
$$
最后，让我们以两道练习题作为速通积分的最后一关：

1. $\int \frac{\ln(8x+8)}{x+1}\cdot dx$
2. $\int e^{kx}\sin(\omega x+\varphi)$