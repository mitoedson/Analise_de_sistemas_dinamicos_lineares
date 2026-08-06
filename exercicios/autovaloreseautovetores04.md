<h1>Autovalores, Autovetores e Estabilidade - Exercício</h1>

Considere o sistema: 

```math
\begin{cases}\frac{dx}{dt} = 2x + 3y \\
\frac{dy}{dt} = 2x + y \end{cases}
```

**Matriz:**

$$A = \begin{bmatrix} 2 & 3 \\ 2 & 1 \end{bmatrix}$$

**Autovalores:** Resolvendo $\det(A-\lambda I)=0$, obtemos $\lambda_1 = -1$ (estável) e $\lambda_2 = 4$ (instável). O sistema total é 
<b>instável</b>.

**Autovetores:** Para $\lambda_1 = -1$, o autovetor é 

$$K_1 = \begin{bmatrix} 1 \\ -1 \end{bmatrix}$$

Para $\lambda_2 = 4$, o autovetor é:

$$K_2 = \begin{bmatrix} 3 \\ 2\end{bmatrix}$$

---

[Ver teoria](teoria/autovaloreseautovetores.md)
