<h1>Estabilidade 06</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente  
2. **Calcular a matriz Jacobiana** do sistema:  

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)

## (f): $\dot x=x-x^2-xy,\quad \dot y=3y-xy-2y^2$

### Passo 1 — Pontos críticos

Fatorando cada equação:
$$\dot x=x(1-x-y)=0 \;\Rightarrow\; x=0 \text{ ou } 1-x-y=0$$
$$\dot y=y(3-x-2y)=0 \;\Rightarrow\; y=0 \text{ ou } 3-x-2y=0$$

Combinando os 4 casos:

- $x=0$ e $y=0$ → **$(0,0)$**
- $x=0$ e $3-x-2y=0$ → $y=3/2$ → **$(0,3/2)$**
- $1-x-y=0$ e $y=0$ → $x=1$ → **$(1,0)$**
- $1-x-y=0$ e $3-x-2y=0$ → resolvendo o sistema: $x=-1,\ y=2$ → **$(-1,2)$**

**Pontos críticos: $(0,0)$, $(0,3/2)$, $(1,0)$, $(-1,2)$**

### Passo 2 — Jacobiano genérico

```math
J(x,y) = \begin{pmatrix} 1-2x-y & -x \\-y & 3-x-4y \end{pmatrix}
```

### Passo 3 — Avaliando em $(0,0)$

```math
J(0,0) = \begin{pmatrix} 1&0 \\ 0&3 \end{pmatrix}
```

$$T=1+3=4,\qquad D=(1)(3)-(0)(0)=3$$

$D>0$; $T^2-4D=16-12=4>0$ (reais); $T>0$ → **nó instável** ✓

### Passo 4 — Avaliando em $(0,3/2)$

```math
J(0,3/2) = \begin{pmatrix} 1 - 3/2 & 0 \\ -3/2 & 3-6 \end{pmatrix} = \begin{pmatrix} -1/2 & 0 \\ -3/2 & -3 \end{pmatrix}
```
$$T=-\frac12-3=-\frac72,\qquad D=\left(-\frac12\right)(-3)-(0)\left(-\frac32\right)=\frac32$$

$D>0$; $T^2-4D=\frac{49}{4}-6=\frac{25}{4}>0$ (reais); $T<0$ → **nó estável** ✓

### Passo 5 — Avaliando em $(1,0)$

$$J(1,0)=\begin{bmatrix}1-2&-1\\0&3-1\end{bmatrix}=\begin{bmatrix}-1&-1\\0&2\end{bmatrix}$$

$$T=-1+2=1,\qquad D=(-1)(2)-(-1)(0)=-2$$

$D<0$ → **sela** ✓

### Passo 6 — Avaliando em $(-1,2)$

$$J(-1,2)=\begin{bmatrix}1+2-2&1\\-2&3+1-8\end{bmatrix}=\begin{bmatrix}1&1\\-2&-4\end{bmatrix}$$

$$T=1-4=-3,\qquad D=(1)(-4)-(1)(-2)=-4+2=-2$$

$D<0$ → **sela** ✓

### Conclusão

$$(0,0):\ \textbf{nó instável} \qquad (0,3/2):\ \textbf{nó estável} \qquad (1,0):\ \textbf{sela} \qquad (-1,2):\ \textbf{sela}$$

