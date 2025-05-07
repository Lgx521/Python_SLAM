# Camera and Image

## 像素坐标系
原点 $o'$ 位于图像的左上角，u轴向右与x轴平行，v轴向下与y轴平行。  
像素坐标系与成像平面之间，相差了一个缩放和原点的平移。  
- 变换矩阵
$$
Z\begin{bmatrix}u\\v\\1\end{bmatrix}=
\begin{bmatrix}
f_x & 0 & c_x \\
0 & f_y & c_y \\
0 & 0 & 1
\end{bmatrix}\begin{bmatrix}X\\Y\\Z\end{bmatrix}\equiv KP
$$
其中的 $3\times3$ 矩阵称为 **相机的内参数矩阵K**  
