<h1>Método de Krasovskii - 01</h1>

Considere o sistema não linear
```math
\begin{cases}\dot x_1 = −4x_1 + x_2 \\ \dot x_2 = x_1 − 4x_2 − x_2^3 \end{cases}
```

Use o método de Krasovskii com $$V(x) = f^T(x)f(x)$$ para mostrar que a origem é assintoticamente estável

---

O vetor de campo é: 
```math
f(x) = \begin{bmatrix} -4x_1+x_2 \\ x_1-4x_2-x_2^3 \end{bmatrix} 
```

Matriz Jacobiana:
```math
A(x) = \frac{\partial f}{\partial x} = \begin{bmatrix} \frac{\partial -4x_1+x_2}{\partial x_1} & \frac{\partial -4x_1+x_2}{\partial x_2} \\ \frac{\partial x_1-4x_2-x_2^3}{\partial x_1} & \frac{\partial x_1-4x_2-x_2^3}{\partial x_2} \end{bmatrix} = \begin{bmatrix} -4 & 1 \\ 1 & -4-3x_2^2 \end{bmatrix}
```

$F(x) = A(x) + A^T(x)$

```math
F(x) = \begin{bmatrix} -4 & 1 \\ 1 & -4-3x_2^2 \end{bmatrix} + \begin{bmatrix} -4 & 1 \\ 1 & -4-3x_2^2 \end{bmatrix} = \begin{bmatrix} -8 & 2 \\ 2 & -8-6x_2^2 \end{bmatrix}
```


Verificar se F(x) < 0 (negativa definida), quando $$F_{11}<0$$ e $$det(F)>0$$:

$$F_{11}= -8 < 0$$
$$det(F) = (-8)(-8-6x_2^2) - (2)(2) = 60 + 48x_2^2 > 0$$

Portanto, F(x) < 0, para todo x

A escolha $$V(x) = f^T(x)f(x)$$:
```math
V(x) = f^T(x)f(x) = \begin{bmatrix} -4x_1+x_2 && x_1-4x_2-x_2^3 \end{bmatrix} \begin{bmatrix} -4x_1+x_2 \\ x_1-4x_2-x_2^3 \end{bmatrix} = (-4x_1+x_2)^2 + (x_1-4x_2-x_2^3)^2
```

Como a origem é o único ponto onde f(x) = 0, temos:
```math
V(x)>0 \quad\text{para}\quad x \ne 0.
```

A derivada de $$\dot V$$:
```math
\dot V = f^T[A(x)+A^T(x)]f(x) = \begin{bmatrix} -4x_1+x_2 && x_1-4x_2-x_2^3 \end{bmatrix} \begin{bmatrix} -8 & 2 \\ 2 & -8-6x_2^2 \end{bmatrix} \begin{bmatrix} -4x_1+x_2 \\ x_1-4x_2-x_2^3 \end{bmatrix} =
```
```math
 =(−152x_1x^2​+196x_1​x_2​−152x_2^2​)+x_2^2​(−6x_1^2​+80x_1​x_2​+12x_1​x_2^3​)−164x_2^4​−56x_2^6​−6x_2^8​
```

$$\dot V < 0,\quad\text{para}\quad x |ne 0$$


Portanto,
$$V(x) > 0, \dot V < 0, x |ne 0$$. (0,0) é assintoticamente estável.


Além disso, como F(x) < 0 para todo x e V (x) → ∞ quando ∥x∥ → ∞, conclui-se que a estabilidade é global.
(0, 0) é globalmente assintoticamente estável.

