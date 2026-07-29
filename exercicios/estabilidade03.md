<h1>Estabilidade 03</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente  
2. **Calcular a matriz Jacobiana** do sistema:  
```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)


## (c) $\dot x=(1+x)\ \text{sen}(y),\quad \dot y=1-x-\cos(y)$

### Passo 1 — Pontos críticos

Da primeira equação: $(1+x)\ \text{sen}(y)=0$, obtem-se 
$$x=-1 \quad \text{ou} \quad \text{sen}(y)=0 \Rightarrow y=m\pi,\ m\in\mathbb{Z}$$

Da segunda equação: $x=1-\cos(y)$



**Caso $x=-1$:** substituindo, $-1=1-\cos(y)\Rightarrow\cos(y)=2$ — **impossível** (cosseno está entre $-1$ e $1$). Descartado.

**Caso $y=m\pi$:** substituindo, $x=1-\cos(m\pi)$

- $m$ **par** ($m=2k$): $\cos(2k\pi)=1\Rightarrow x=0$ → pontos $(0,2k\pi)$
- $m$ **ímpar** ($m=2k+1$): $\cos((2k+1)\pi)=-1\Rightarrow x=2$ → pontos $(2,(2k+1)\pi)$

**Pontos críticos: $(0,2k\pi)$ e $(2,(2k+1)\pi)$, $k\in\mathbb Z$**

### Passo 2 — Jacobiano genérico

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial}{\partial x}\left[(1+x)\text{sen}(y)\right] & \dfrac{\partial}{\partial y}\left[(1+x)\text{sen}(y)\right] \\ \dfrac{\partial}{\partial x}\left[1-x-\cos(y)\right] & \dfrac{\partial}{\partial y}\left[1-x-\cos(y)\right] \end{pmatrix} 
```

```math
J(x,y) = \begin{pmatrix} \text{sen}(y) & (1+x)\cos(y) \\ -1 & \text{sen}(y) \end{pmatrix}
```

**Observação importante:** em **todos** os pontos críticos, $y=m\pi$, e $\text{sen}(m\pi)=0$ sempre. Isso simplifica bastante a avaliação — a diagonal principal do Jacobiano sempre zera nos pontos críticos!

### Passo 3 — Avaliando na família $(0, 2k\pi)$

Aqui $x=0$, $y=2k\pi$ (par), então $\cos(2k\pi)=1$:

```math
J(0,2k\pi) = \begin{pmatrix} 0 & (1+0)(1) \\ -1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & 1 \\ -1 & 0 \end{pmatrix}
```

**Traço e determinante:** $$T=0+0=0, D=(0)(0)-(1)(-1)=1$$

Autovalores: $$\lambda^2+1=0 \;\Rightarrow\; \lambda=\pm i$$

$T=0$ e $D=1>0$ → **centro**

### Passo 4 — Avaliando na família $(2,(2k+1)\pi)$

Aqui $x=2$, $y=(2k+1)\pi$ (ímpar), então $\cos((2k+1)\pi)=-1$:

```math
J(2,(2k+1)\pi) = \begin{pmatrix} 0 & (1+2)(-1) \\ -1 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -3 \\ -1 & 0 \end{pmatrix}
```

**Traço e determinante:** $$T=0+0=0, D=(0)(0)-(-3)(-1)=-3$$

Autovalores: $$\lambda^2-3=0 \;\Rightarrow\; \lambda=\pm\sqrt3$$

$T=0$ e $D=-3<0$ → **sela**

### Conclusão final

$$(0,2m\pi):\ \textbf{centro} \qquad\qquad (2,(2m+1)\pi):\ \textbf{sela}$$


