<h1>Estabilidade 07</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente  
2. **Calcular a matriz Jacobiana** do sistema:  

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)

## (h): $\dot x=x-x^2-xy,\quad \dot y=\dfrac12y-\dfrac14y^2-\dfrac34xy$

### Passo 1 — Pontos críticos

Fatorando cada equação:

$$\dot x=x(1-x-y)=0 \;\Rightarrow\; x=0 \text{ ou } 1-x-y=0$$

$$\dot y=y\left(\frac12-\frac14y-\frac34x\right)=0 \;\Rightarrow\; y=0 \text{ ou } \frac12-\frac14y-\frac34x=0$$

Multiplicando essa segunda condição por 4 (para limpar frações): $2-y-3x=0 \Rightarrow y=2-3x$

### Passo 2 — Combinando os 4 casos

**Caso 1: $x=0$ e $y=0$**
→ **$(0,0)$**

**Caso 2: $x=0$ e $y=2-3x$**
→ $y=2-3(0)=2$ → **$(0,2)$**

**Caso 3: $1-x-y=0$ e $y=0$**
→ $x=1$ → **$(1,0)$**

**Caso 4: $1-x-y=0$ e $y=2-3x$**
→ substituindo: $1-x-(2-3x)=0 \Rightarrow 1-x-2+3x=0 \Rightarrow 2x-1=0 \Rightarrow x=\dfrac12$
→ $y=1-\dfrac12=\dfrac12$ → **$(1/2,1/2)$**

**Pontos críticos: $(0,0)$, $(0,2)$, $(1,0)$, $(1/2,1/2)$** ✓ (bate com o gabarito)

### Passo 3 — Jacobiano genérico

```math
J(x,y) = \begin{pmatrix} 1-2x-y & -x\\ -\frac{3}{4}y & \frac{1}{2}-\frac{1}{2}y-\frac{3}{4}x \end{pmatrix}
```

### Passo 4 — Avaliando em $(0,0)$

```math
J(0,0) = \begin{pmatrix} 1 & 0 \\ 0 & \frac{1}{2} \end{pmatrix}
```

$$T=1+\frac12=\frac32,\qquad D=(1)\left(\frac12\right)-(0)(0)=\frac12$$

$D>0$; $T^2-4D=\frac94-2=\frac14>0$ (reais); $T>0$ → **nó instável** ✓

### Passo 5 — Avaliando em $(0,2)$

```math
J(0,2) = \begin{pmatrix} 1-2 & 0 \\ \frac{-3}{2} & \frac{1}{2}-1 \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ \frac{-3}{2}& \frac{-1}{2} \end{pmatrix}
```

$$T=-1-\frac12=-\frac32,\qquad D=(-1)\left(-\frac12\right)-(0)\left(-\frac32\right)=\frac12$$

$D>0$; $T^2-4D=\frac94-2=\frac14>0$ (reais); $T<0$ → **nó estável** 

### Passo 6 — Avaliando em $(1,0)$

```math
J(1,0) = \begin{pmatrix} 1-2&-1\\0&1/2-3/4\end{bmatrix}=\begin{bmatrix}-1&-1\\0&-1/4 \end{pmatrix}
```

$$T=-1-\frac14=-\frac54,\qquad D=(-1)\left(-\frac14\right)-(-1)(0)=\frac14$$

$D>0$; $T^2-4D=\frac{25}{16}-1=\frac{9}{16}>0$ (reais); $T<0$ → **nó estável**

### Passo 7 — Avaliando em $(1/2,1/2)$

```math
J(\frac{1}{2},\frac{1}{2}) = \begin{pmatrix} 1-1-1/2 & -1/2\\-3/8 & 1/2-1/4-3/8\end{bmatrix}=\begin{bmatrix}-1/2&-1/2\\-3/8&-1/8\end{pmatrix}
```

$$T=-\frac12-\frac18=-\frac58,\qquad D=\left(-\frac12\right)\left(-\frac18\right)-\left(-\frac12\right)\left(-\frac38\right)=\frac{1}{16}-\frac{3}{16}=-\frac{2}{16}=-\frac18$$

$D=-\dfrac18<0$ → **sela** 

### Conclusão

$$(0,0):\textbf{nó instável} \quad (0,2):\textbf{nó estável} \quad (1,0):\textbf{nó estável} \quad (1/2,1/2):\textbf{sela}$$
---

Esse item mostra que o processo é o mesmo mesmo com frações — só exige mais cuidado na aritmética. Quer revisar mais algum item?
