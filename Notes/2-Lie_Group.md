# Mathematics

## Group
1. 封闭性 $\forall a_1, a_2 \in A, \quad a_1\cdot a_2\in A$  
2. 结合律 
3. Identical Element  $\exists a_0 \in A,\space s.t.\space \forall a\in A, \quad a_0 \cdot a = a\cdot a_0 = a$
4. 逆 $\forall a\in A,\quad \exists a^{-1}\in A, \space s.t. \space a\cdot a^{-1}=a_0$

## Lie Group and Lie Algebra

- to be continued

## Exponetional and Logarithm Mapping

- 指数映射：将李代数映射回李群
- 对数映射：将李群映射为李代数
- 实际上，旋转矩阵与旋转向量之间的转换就是李群与李代数的转换

---
- Exponential mapping:  
$$ 
\exp(\boldsymbol{\phi^\wedge}) = \sum_{n=0}^\infty{\frac{1}{n!}(\phi^\wedge)^n}
$$
- Suppose $\phi = \theta \boldsymbol{a}$  
Where $\theta$ is mudule and $\boldsymbol{a}$ is direction.
- Use some tricks:  
$$
(a^\wedge)^2=aa^T-I
$$
$$
(a^\wedge)^3=-a^\wedge
$$

- Therefore
$$
\begin{aligned}
\exp(\phi^\wedge)&=\exp(\theta \bold{a}^\wedge)=\sum_{n=0}^\infty{\frac{1}{n!}(\theta \bold{a}^\wedge)^n} \\
&=\boldsymbol{I}+\theta \boldsymbol{a}^{\wedge}+\frac{1}{2!} \theta^{2} \boldsymbol{a}^{\wedge} \boldsymbol{a}^{\wedge}+\frac{1}{3!} \theta^{3} \boldsymbol{a}^{\wedge} \boldsymbol{a}^{\wedge} \boldsymbol{a}^{\wedge}+\frac{1}{4!} \theta^{4}\left(\boldsymbol{a}^{\wedge}\right)^{4}+\cdots \\
&=\boldsymbol{a} \boldsymbol{a}^{\mathrm{T}}-\boldsymbol{a}^{\wedge} \boldsymbol{a}^{\wedge}+\theta \boldsymbol{a}^{\wedge}+\frac{1}{2!} \theta^{2} \boldsymbol{a}^{\wedge} \boldsymbol{a}^{\wedge}-\frac{1}{3!} \theta^{3} \boldsymbol{a}^{\wedge}-\frac{1}{4!} \theta^{4}\left(\boldsymbol{a}^{\wedge}\right)^{2}+\cdots \\
&={a}^{\wedge}{a}^{\wedge}+\bold{I}+\sin\theta{a}^{\wedge}-\cos\theta{a}^{\wedge}{a}^{\wedge}\\
&= \cos\theta \bold{I} + (1-\cos\theta) \bold{aa}^T+\sin\theta {a}^{\wedge}
\end{aligned}
$$

可以看出，此表达式与Rogrigue's formula形式相同，李代数$\mathfrak{s0}(3)$ 实际上就是旋转向量组成的空间。 

- For transform matrix  
    - 李代数 $\mathfrak{se}(3)$
    $$\xi^{\wedge}=
    \begin{bmatrix}
    \phi^{\wedge} & \rho \\
    \mathbf{0}^{\mathrm{T}} & 0
    \end{bmatrix}\in\mathbb{R}^{4\times4}
    $$
    这里的$^\wedge$表示向量映射为矩阵而非反对称

    - 指数映射  
    $$
    \begin{aligned}
    \exp\left(\xi^{\wedge}\right)&=
    \begin{bmatrix}
    \sum_{n=0}^{\infty}\frac{1}{n!}{\left(\phi^{\wedge}\right)}^{n} & \sum_{n=0}^{\infty}\frac{1}{\left(n+1\right)!}{\left(\phi^{\wedge}\right)}^{n}\boldsymbol{\rho} \\
    \mathbf{0}^{\mathrm{T}} & 1
    \end{bmatrix} \\
    &\triangleq
    \begin{bmatrix}
    R & J\rho \\
    \\
    \mathbf{0}^\mathrm{T} & 1
    \end{bmatrix}=\boldsymbol{T}.
    \end{aligned}
    $$
    After similar derivative, we can obtain $J$
    $$
    \boldsymbol{J}=\frac{\sin\theta}{\theta}\boldsymbol{I}+\left(1-\frac{\sin\theta}{\theta}\right)\boldsymbol{a}\boldsymbol{a}^\mathrm{T}+\frac{1-\cos\theta}{\theta}\boldsymbol{a}^\wedge
    $$

![relation](./images/relation.png)

---

## 李代数求导--扰动模型
Aiming at take the derivative:
$$
\frac{\partial(\exp(\phi^\wedge)\boldsymbol{p})}{\partial\phi}
$$
我们对$\boldsymbol{R}$进行一个微扰，以左扰动为例，左乘一个微扰对应的李代数$\varphi$，求导，有：
$$
\begin{aligned}
\frac{\partial(\boldsymbol{R} \boldsymbol{p})}{\partial \varphi} & =\lim _{\varphi \rightarrow 0} \frac{\exp \left(\boldsymbol{\varphi}^{\wedge}\right) \exp \left(\phi^{\wedge}\right) \boldsymbol{p}-\exp \left(\phi^{\wedge}\right) \boldsymbol{p}}{\boldsymbol{\varphi}} \\
& =\lim _{\varphi \rightarrow 0} \frac{\left(\boldsymbol{I}+\varphi^{\wedge}\right) \exp \left(\phi^{\wedge}\right) \boldsymbol{p}-\exp \left(\phi^{\wedge}\right) \boldsymbol{p}}{\varphi} \\
& =\lim _{\varphi \rightarrow 0} \frac{\varphi^{\wedge} \boldsymbol{R} \boldsymbol{p}}{\varphi}=\lim _{\varphi \rightarrow 0} \frac{-(\boldsymbol{R} \boldsymbol{p})^{\wedge} \varphi}{\boldsymbol{\varphi}}\\
&=-(\boldsymbol{R} \boldsymbol{p})^{\wedge}
\end{aligned}
$$

