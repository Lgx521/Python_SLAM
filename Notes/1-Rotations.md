# Mathematics

## Rotation of rigid body  

### New definition on cross product

$$
\boldsymbol{a}\times \boldsymbol{b} = \begin{Vmatrix}
\hat{i}  &\hat{j}  &\hat{k} \\
a_1  &a_2  &a_3 \\
b_1  &b_2  &b_3
\end{Vmatrix}
= \begin{bmatrix}
0 & -a_3 & a_2 \\
a_3 & 0 & -a_1 \\
-a_2 & a_1 & 0 
\end{bmatrix} \boldsymbol{b} \equiv \boldsymbol{a}^\wedge \boldsymbol{b}
$$

Where we can import the $^\wedge$ symbol to reconstruct 3D vector $\boldsymbol{a}$ to and skew-symmetric matrix.  

$$
\boldsymbol{a}^\wedge = \begin{bmatrix} a_1 \\ a_2 \\ a_3 \end{bmatrix} ^\wedge = \begin{bmatrix}
0 & -a_3 & a_2 \\
a_3 & 0 & -a_1 \\
-a_2 & a_1 & 0 
\end{bmatrix}
$$

### Special Orthogonal Group
- Rotation Matrix  
$$
SO(n)=\{\boldsymbol{R}\in \mathbb{R}^{n\times n} | \boldsymbol{RR}^T=\boldsymbol{I},det(\boldsymbol{R})=1\}
$$
For rotation matrix, $n=3$.

### Special Euclidian Group
- Transform Matrix  
$$
\boldsymbol{T}=\begin{bmatrix}
\boldsymbol{R} & \boldsymbol{t} \\
\boldsymbol{0}^T & 1 \end{bmatrix}
$$

$$
SE(n)=\{\boldsymbol{T}\in \mathbb{R}^{4\times 4} | \boldsymbol{R}\in \mathrm{SO}(3),\boldsymbol{t}\in \mathbb{R}^{3}\}
$$

- Inverse of $\boldsymbol{T}$   
$$
\boldsymbol{T}^{-1}=
\begin{bmatrix}
\boldsymbol{R}^T & -\boldsymbol{R}^T\boldsymbol{t} \\
\boldsymbol{0}^T & 1 \end{bmatrix}
$$

### Rotational vector
- Rodrigues's formula:   
$$
\boldsymbol{R}=\cos\theta\boldsymbol{I}+(1-\cos\theta)\boldsymbol{nn}^T+\sin\theta \boldsymbol{n}^\wedge
$$
Which shows that any rotation can be represented by a **rotation axis** and **rotation angle**, $\boldsymbol{n}$ and $\theta$ respectively.  

Take trace both side, we can get that:
$$
\theta = \arccos\frac{tr(\boldsymbol{R})-1}{2}
$$


## Quaternion
- Expression  
$$
\boldsymbol{q}=q_0+q_1 i+q_2 j+q_3 k=[s,\boldsymbol{v}]^T
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
\boldsymbol{q}_a \boldsymbol{q}_b=[s_as_b-\boldsymbol{v}_a^T\boldsymbol{v_b},\space s_a\boldsymbol{v}_b+s_b\boldsymbol{v}_a+\boldsymbol{v}_a\times\boldsymbol{v}_b]^T
$$

- Module  
$$
||\boldsymbol{q}||=\sqrt{s_a^2+||\boldsymbol{v}||^2}
$$

It is verified that:
$$
||\boldsymbol{q}_a\boldsymbol{q}_b||=||\boldsymbol{q}_a||\cdot||\boldsymbol{q}_b||
$$

- Conjugate: Opposite the imaginary part  
$$
\boldsymbol{q}_a^*=[s_a,-v_a]^T
$$

- Inverse  
$$
\boldsymbol{q}^{-1}=\frac{\boldsymbol{q}^*}{||\boldsymbol{q}||^2}
$$


### Represent rotation with quaternion

- 三维空间中的点可以用一个虚四元数表示  
$$
\boldsymbol{p}=[0,x,y,z]^T
$$
- 任意单位四元数表示一个旋转  
$$
\boldsymbol{p}'=\boldsymbol{qpq}^{-1}
$$
- 把四元数乘法写成矩阵乘法的形式   
Define:
$$
\boldsymbol{q}^+=\begin{bmatrix}
s & -\boldsymbol{v}^T \\
\boldsymbol{v} & s\boldsymbol{I}+\boldsymbol{v}^\wedge\end{bmatrix}
$$

$$
\boldsymbol{q}^\oplus=\begin{bmatrix}
s & -\boldsymbol{v}^T \\
\boldsymbol{v} & s\boldsymbol{I}-\boldsymbol{v}^\wedge\end{bmatrix}
$$

- It is verified that  
$$
\boldsymbol{q}_1\boldsymbol{q}_2=\boldsymbol{q}_1^+\boldsymbol{q}_2=\boldsymbol{q}_2^\oplus\boldsymbol{q}_1
$$

### Rotational matrix from quaternion
After brief derivation    
$$
\boldsymbol{R} = \boldsymbol{vv}^T+s^2\boldsymbol{I}+2s\boldsymbol{v}^\wedge+(\boldsymbol{v}^\wedge)^2
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
\boldsymbol{n}=\frac{\begin{bmatrix}q_1,q_2,q_3\end{bmatrix}^T}{\sin\frac\theta 2}
$$

## 射影变换
$$
\boldsymbol{T}_p=\begin{bmatrix}
\boldsymbol{A} & \boldsymbol{t} \\
\boldsymbol{a}^T & v\end{bmatrix}
$$
- Invariance: 接触的平面的相交及相切特性  


