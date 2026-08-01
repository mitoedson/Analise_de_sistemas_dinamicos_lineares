<h1>Estabilidade Local - 06</h1>

Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

$\dot x=x-x^2-xy,\quad \dot y=3y-xy-2y^2$

---

### Passo 1 — Pontos críticos

Fatorando cada equação:
$$\dot x=x(1-x-y)=0 \;\Rightarrow\; x=0 \text{ ou } 1-x-y=0$$
$$\dot y=y(3-x-2y)=0 \;\Rightarrow\; y=0 \text{ ou } 3-x-2y=0$$

Combinando os 4 casos:

- $x=0$ e $y=0$ → **$(0,0)$**
- $x=0$ e $3-x-2y=0$ → $y=3/2$ → **$(0,\frac{3}{2})$**
- $1-x-y=0$ e $y=0$ → $x=1$ → **$(1,0)$**
- $1-x-y=0$ e $3-x-2y=0$ → resolvendo o sistema: $x=-1,\ y=2$ → **$(-1,2)$**

**Pontos críticos: $(0,0)$, $(0,\frac{3}{2})$, $(1,0)$, $(-1,2)$**

### Passo 2 — Jacobiano genérico

```math
J(x,y) = \begin{pmatrix} 1-2x-y & -x \\-y & 3-x-4y \end{pmatrix}
```

### Passo 3 — Avaliando através dos pontos críticos

### Em $(0,0)$:

```math
J(0,0) = \begin{pmatrix} 1&0 \\ 0&3 \end{pmatrix}
```

$T=1+3=4, D=(1)(3)-(0)(0)=3$

Autovalores: $$\lambda^2-4\lambda+3=0 \;\Rightarrow\; \lambda=\frac{4\pm\sqrt{16-12}}{2}=\frac{4\pm2}{2} \;\Rightarrow\; \lambda_1=3,\ \lambda_2=1$$

$D>0$; $T^2-4D=16-12=4>0$ (reais); $T>0$ → **nó instável**

### Em $(0, \frac{3}{2})$:

```math
J(0,3/2) = \begin{pmatrix} 1 - \frac{3}{2} & 0 \\ -\frac{3}{2} & 3-6 \end{pmatrix} = \begin{pmatrix} -\frac{1}{2} & 0 \\ -\frac{3}{2} & -3 \end{pmatrix}
```
$T=-\frac12-3=-\frac72, D=\left(-\frac12\right)(-3)-(0)\left(-\frac32\right)=\frac32$

Autovalores: $$\lambda^2+\frac72\lambda+\frac32=0 \;\Rightarrow\; \lambda=\frac{-\frac72\pm\sqrt{\frac{49}{4}-6}}{2}=\frac{-\frac72\pm\frac52}{2} \;\Rightarrow\; \lambda_1=-\frac12,\ \lambda_2=-3$$

$D>0$; $T^2-4D=\frac{49}{4}-6=\frac{25}{4}>0$ (reais); $T<0$ → **nó estável**

### Em $(1,0)$:

```math
J(1,0) = \begin{pmatrix} 1-2 & -1 \\ 0 & 3-1 \end{pmatrix} = \begin{pmatrix} -1 & -1 \\ 0 & 2 \end{pmatrix}
```

$T=-1+2=1, D=(-1)(2)-(-1)(0)=-2$

Autovalores: $$\lambda^2-\lambda-2=0 \;\Rightarrow\; \lambda=\frac{1\pm\sqrt{1+8}}{2}=\frac{1\pm3}{2} \;\Rightarrow\; \lambda_1=2,\ \lambda_2=-1$$

$D<0$ → **sela** 

### Em $(-1,2)$:

```math
J(-1,2) = \begin{pmatrix} 1+2-2 & 1 \\ -2 & 3+1-8 \end{pmatrix} = \begin{pmatrix} 1 & 1 \\ -2 & -4 \end{pmatrix}
```

$T=1-4=-3, D=(1)(-4)-(1)(-2)=-4+2=-2$

Autovalores: $$\lambda^2+3\lambda-2=0 \;\Rightarrow\; \lambda=\frac{-3\pm\sqrt{9+8}}{2}=\frac{-3\pm\sqrt{17}}{2}$$

$D<0$ → **sela** 

### Conclusão

$$(0,0):\ \textbf{nó instável} \qquad (0,\frac{3}{2}):\ \textbf{nó estável} \qquad (1,0):\ \textbf{sela} \qquad (-1,2):\ \textbf{sela}$$

