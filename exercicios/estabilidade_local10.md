<h1>Estabilidade Local - 10</h1>

Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

```math
\dot x=x+x^2+y^2
```
```math
\dot y=y-xy
```

---

### Passo 1 — Pontos críticos

Da segunda equação:
$$y-xy=0 \Rightarrow y(1-x)=0 \Rightarrow y=0 \text{ ou } x=1$$

**Caso $y=0$:** substituindo na primeira equação: $x+x^2=0 \Rightarrow x(1+x)=0 \Rightarrow x=0$ ou $x=-1$

→ pontos $(0,0)$ e $(-1,0)$

**Caso $x=1$:** substituindo na primeira equação: $1+1+y^2=0 \Rightarrow y^2=-2$ — impossível (sem solução real). Descartado.

**Pontos críticos: $(0,0)$ e $(-1,0)$**

### Passo 2 — Jacobiano genérico

```math
J(x,y)=\begin{pmatrix} 1+2x & 2y \\ -y & 1-x \end{pmatrix}
```

### Passo 3 — Avaliando nos pontos críticos:

### Em $(0,0)$:

```math
J(0,0)=\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}
```

$T=1+1=2, D=(1)(1)-(0)(0)=1$

Autovalores: $$\lambda=1 \text{ (duplo)}$$

$D>0$; $T^2-4D=4-4=0$ → autovalores reais **repetidos**: $\lambda=\dfrac{T}{2}=1$ (duplo); $T>0$ → **nó impróprio instável**

### Em $(-1,0)$:

```math
J(-1,0)=\begin{pmatrix} 1-2 & 0 \\ 0 & 1+1 \end{pmatrix}=\begin{pmatrix} -1 & 0 \\ 0 & 2 \end{pmatrix}
```

$T=-1+2=1, D=(-1)(2)-(0)(0)=-2$

Autovalores: $$\lambda_1=2,\ \lambda_2=-1$$

$D<0$ → **sela** 

### Conclusão

$$(0,0):\ \textbf{nó impróprio instável} \qquad\qquad (-1,0):\ \textbf{sela}$$

