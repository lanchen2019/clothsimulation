# ClothSimulation

## Energy Term

### bending force

Hinge-edge model 

<img src="https://user-images.githubusercontent.com/46516710/145521649-2d204715-0c23-4d4c-9832-d1fa0bded459.png" title="" alt="image" width="209">

Given two triangles $t_0, t_1$, $e_0$ is the shared edge, four vertices are $x_0, x_1, x_2,x_3$，$A_0,A_1$ are the areas of $t_0, t_1$.

The Hessian matrix is computed by $Q(e_0)=\frac{3}{(A_0+A_1)}K_0^TK_0$ $(4 \times 4)$
  $K=(c_{03}+ c_{04}, c_{01}+ c_{02}, -c_{01}-c_{03}, -c_{02}-c_{04})$

$c_{ij} = cot(e_i, e_j)$
$E=-\frac{1}{2}(x_0,x_1,x_2,x_3)Q(e_0)(x_0,x_1,x_2,x_3)^T$  $(3\times3)$

$F=-Q(e_0)(x_0,x_1,x_2,x_3)^T$($4\times3$, then add force to four vertices).

### stretching force

## PDE

## linear solver

## collision

## update

# Houdini Learning

## Draping cloth with 5 different materials
