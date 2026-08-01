<h1>Estabilidade Local - 07</h1>

Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

$\dot x=1-y,\quad \dot y=x^2-y^2$

--- 

### Passo 1 — Pontos críticos

Da primeira equação: $1-y=0 \Rightarrow y=1$

Substituindo na segunda: $x^2-1^2=0 \Rightarrow x^2=1 \Rightarrow x=\pm1$

**Pontos críticos: $(-1,1)$ e $(1,1)$**

### Passo 2 — Jacobiano genérico

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial}{\partial x}(1-y) & \dfrac{\partial}{\partial y}(1-y) \\ \dfrac{\partial}{\partial x}(x^2-y^2) & \dfrac{\partial}{\partial y}(x^2-y^2) \end{pmatrix} = \begin{pmatrix}0&-1\\2x&-2y\end{pmatrix}
```

### Passo 3 — Avaliando em $(-1,1)$

```math
J(-1,1) = \begin{pmatrix} 0&-1\\-2&-2\end{pmatrix}
```

$T=0+(-2)=-2, D=(0)(-2)-(-1)(-2)=0-2=-2$

Autovalores: $$\lambda^2+2\lambda-2=0 \;\Rightarrow\; \lambda=\frac{-2\pm\sqrt{4+8}}{2}=-1\pm\sqrt3$$

$D=-2<0$ → **sela** (independente de $T$)

### Passo 4 — Avaliando em $(1,1)$

```math
J(1,1) = \begin{pmatrix} 0&-1\\2&-2\end{pmatrix}
```

$T=0+(-2)=-2, D=(0)(-2)-(-1)(2)=0+2=2$

Autovalores: $$\lambda^2+2\lambda+2=0 \;\Rightarrow\; \lambda=\frac{-2\pm\sqrt{4-8}}{2}=-1\pm i$$

$D=2>0$; $T^2-4D=4-8=-4<0$ → autovalores **complexos**; $T=-2<0$ → **foco estável**

### Conclusão

$$(-1,1):\ \textbf{sela} \qquad\qquad (1,1):\ \textbf{foco estável}$$
