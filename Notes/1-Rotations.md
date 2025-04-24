# Mathematics

## Rotation of rigid body  

### New definition on cross product

$$
\bold{a}\times \bold{b} = \begin{Vmatrix}
\hat{i}  &\hat{j}  &\hat{k} \\
a_1  &a_2  &a_3 \\
b_1  &b_2  &b_3
\end{Vmatrix}
= \begin{bmatrix}
0 & -a_3 & a_2 \\
a_3 & 0 & -a_1 \\
-a_2 & a_1 & 0 
\end{bmatrix} \bold{b} \equiv \bold{a}^\wedge \bold{b}
$$

Where we can import the $^\wedge$ symbol to reconstruct 3D vector $\bold{a}$ to and skew-symmetric matrix.  

$$
\bold{a}^\wedge = \begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix} ^\wedge = \begin{bmatrix}
0 & -a_3 & a_2 \\
a_3 & 0 & -a_1 \\
-a_2 & a_1 & 0 
\end{bmatrix}
$$

### Special Orthogonal Group
- Rotation Matrix  
$$
SO(n)=\{\bold{R}\in \mathbb{R}^{n\times n} | \bold{RR}^T=\bold{I},det(\bold{R})=1\}
$$
For rotation matrix, $n=3$.

### Special Euclidian Group
- Transform Matrix  
$$
\bold{T}=\begin{bmatrix}
\bold{R} & \bold{t} \\
\bold{0}^T & 1 \end{bmatrix}
$$

$$
SE(n)=\{\bold{T}\in \mathbb{R}^{4\times 4} | \bold{R}\in \mathrm{SO}(3),\bold{t}\in \mathbb{R}^{3}\}
$$

- Inverse of $\bold{T}$   
$$
\bold{T}^{-1}=
\begin{bmatrix}
\bold{R}^T & -\bold{R}^T\bold{t} \\
\bold{0}^T & 1 \end{bmatrix}
$$

### Rotational vector
- Rodrigues's formula:   
$$
\bold{R}=\cos\theta\bold{I}+(1-\cos\theta)\bold{nn}^T+\sin\theta \bold{n}^\wedge
$$
Which shows that any rotation can be represented by a **rotation axis** and **rotation angle**, $\bold{n}$ and $\theta$ respectively.  

Take trace both side, we can get that:
$$
\theta = \arccos\frac{tr(\bold{R})-1}{2}
$$


## Quaternion
- Expression  
$$
\bold{q}=q_0+q_1 i+q_2 j+q_3 k=[s,\bold{v}]^T
$$

$i,j,k$  just like the unit vector in rectangular coordinate, but are imaginary numbers, follows:
$$
i^2=j^2=k^2=-1 \\
ij=k, \quad ji=-k \\
jk=i, \quad kj=-i \\
ki=j, \quad ik=-j
$$

### Computations
- Multiplication  
$$
\bold{q}_a \bold{q}_b=[s_as_b-\bold{v}_a^T\bold{v_b},\space s_a\bold{v}_b+s_b\bold{v}_a+\bold{v}_a\times\bold{v}_b]^T
$$

- Module  
$$
||\bold{q}||=\sqrt{s_a^2+||\bold{v}||^2}
$$

It is verified that:
$$
||\bold{q}_a\bold{q}_b||=||\bold{q}_a||\cdot||\bold{q}_b||
$$

- Conjugate: Opposite the imaginary part  
$$
\bold{q}_a^*=[s_a,-v_a]^T
$$

- Inverse  
$$
\bold{q}^{-1}=\frac{\bold{q}^*}{||\bold{q}||^2}
$$


### Represent rotation with quaternion

- 三维空间中的点可以用一个虚四元数表示  
$$
\bold{p}=[0,x,y,z]^T
$$
- 任意单位四元数表示一个旋转  
$$
\bold{p}'=\bold{qpq}^{-1}
$$
- 把四元数乘法写成矩阵乘法的形式   
Define:
$$
\bold{q}^+=\begin{bmatrix}
s & -\bold{v}^T \\
\bold{v} & s\bold{I}+\bold{v}^\wedge\end{bmatrix}
$$

$$
\bold{q}^\oplus=\begin{bmatrix}
s & -\bold{v}^T \\
\bold{v} & s\bold{I}-\bold{v}^\wedge\end{bmatrix}
$$

- It is verified that  
$$
\bold{q}_1\bold{q}_2=\bold{q}_1^+\bold{q}_2=\bold{q}_2^\oplus\bold{q}_1
$$

### Rotational matrix from quaternion
After brief derivation    
$$
\bold{R} = \bold{vv}^T+s^2\bold{I}+2s\bold{v}^\wedge+(\bold{v}^\wedge)^2
$$

Take the trace, we can obtain  
$$
\theta=2\arccos s
$$

Then the rotation angle and axis is  

$$
\theta=2\arccos q_0
$$

$$
\bold{n}=\frac{\begin{bmatrix}q_1,q_2,q_3\end{bmatrix}^T}{\sin\frac\theta 2}
$$

## 射影变换
$$
\bold{T}_p=\begin{bmatrix}
\bold{A} & \bold{t} \\
\bold{a}^T & v\end{bmatrix}
$$
- Invariance: 接触的平面的相交及相切特性  


