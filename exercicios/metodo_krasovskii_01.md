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
A(x) = \frac{\partial f}{\partial x} = \begin{bmatrix} \frac{\partial -4x_1+x_2}{\partial x_1} & \frac{\partial -4x_1+x_2}{\partial x_2} \\ \frac{\partial x_1-4x_2-x_2^3}{\partial x_1} & \frac{\partial x_1-4x_2-x_2^3}{\partial x_2} \end{bmatrix} 
```

