# ClothSimulation

## Energy Term

### bending force

Hinge-edge model

![image](https://user-images.githubusercontent.com/46516710/145521649-2d204715-0c23-4d4c-9832-d1fa0bded459.png)

Given two triangles $t_0, t_1$, $e_0$ is the shared edge, four vertices are $x_0, x_1, x_2,x_3$，$A_0,A_1$ are the areas of $t_0, t_1$.

The Hessian matrix is computed by $Q(e_0)=\frac{3}{(A_0+A_1)}K_0^TK_0$ $(4 \times 4)$
 $K=(c_{03}+ c_{04}, c_{01}+ c_{02}, -c_{01}-c_{03}, -c_{02}-c_{04})$

$c_{ij} = cot(e_i, e_j)$
Energy $E=-\frac{1}{2}(x_0,x_1,x_2,x_3)Q(e_0)(x_0,x_1,x_2,x_3)^T$ $(3\times3)$

$F=-Q(e_0)(x_0,x_1,x_2,x_3)^T$($4\times3$, then add force to four vertices).

### stretching force

![图片1](https://user-images.githubusercontent.com/46516710/145682140-4ce0e5db-ebcf-41bf-8734-1df08f3b5839.png)

deformation gradient $F=(w_u,w_v)=(\frac{\partial x}{\partial u}, \frac{\partial x}{\partial v})$

$Dm=(u_2-u1, u3-u1)$ 2*2

$invDm = Dm^{-1}$

$F = (x_2-x_1, x_3-x_1) invDm$ 3*2

Green strain tensor $G=(F'F-I)/2=(\begin{matrix} (w_u^2-1)/2 & w_uw_v/2 \\ w_uw_v/2 & (w_v^2-1)/2 \end{matrix})$

Energy is calculated by Green strain tensor:

$E= \mu G:G+\lambda/2 tr^2(G)$

Force $\frac{\partial E}{\partial x}$

## PDE

$M\frac{\partial v_{t+1}}{\partial t} = - F(x_{t+1})+f_{ext}$

implicit intergration

$x_{t+1} = x_t + v_{t+1}*\Delta t$

$\frac{\partial v_{t+1}}{\partial t} = (v_{t+1}-v_t)/\Delta t$

taylor series

$F(x_{t+1})=F(x_t)+F'(x_t)v_{t+1}*\Delta t$

$M(v_{t+1}-v_t)/\Delta t = -F(x_t)-F'(x_t)v_{t+1}*\Delta t+f_{ext}$

$(M+F'(x_t)* \Delta t^2)v_{t+1}=-F(x_t)\Delta t+Mv_t+f_{ext}* \Delta t$

## linear solver

PCG

## collision

## update

# Houdini Learning

## Draping cloth with 5 different materials
