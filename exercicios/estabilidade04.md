<h1>Estabilidade 04</h1>

## Determinar os pontos críticos de cada sistema e investigar a estabilidade local destes pontos:

### Método geral

1. **Encontrar os pontos críticos**: resolver o sistema $\dot x=0,\ \dot y=0$ simultaneamente  
2. **Calcular a matriz Jacobiana** do sistema:  
```math
J(x,y) = \begin{pmatrix} \dfrac{\partial f_1}{\partial x} & \dfrac{\partial f_1}{\partial y} \\ \dfrac{\partial f_2}{\partial x} & \dfrac{\partial f_2}{\partial y} \end{pmatrix}
```

3. **Avaliar $J$ em cada ponto crítico** e calcular seus **autovalores**
4. **Classificar** o ponto crítico conforme os autovalores (sela, nó, foco, centro — estável/instável)


## (d): $\dot x=x+y^2,\quad \dot y=x+y$

### Passo 1 — Pontos críticos

Da segunda equação: $x+y=0 \Rightarrow x=-y$

Substituindo na primeira: $-y+y^2=0 \Rightarrow y(y-1)=0$

- $y=0 \Rightarrow x=0$ → ponto **$(0,0)$**
- $y=1 \Rightarrow x=-1$ → ponto **$(-1,1)$**

**Pontos críticos: $(0,0)$ e $(-1,1)$** 

### Passo 2 — Jacobiano genérico

```math
J(x,y) = \begin{pmatrix} \dfrac{\partial}{\partial x}(x+y^2) & \dfrac{\partial}{\partial y}(x+y^2) \\ \dfrac{\partial}{\partial x}(x+y) & \dfrac{\partial}{\partial y}(x+y) \end{pmatrix} = \begin{pmatrix}1&2y\\1&1\end{pmatrix}
```

### Passo 3 — Avaliando em $(0,0)$

```math
J(0,0)=\begin{pmatrix}1&0\\1&1\end{pmatrix}
```

$T=1+1=2, D=(1)(1)-(0)(1)=1$

Autovalores: $$\lambda^2-2\lambda+1=0 \;\Rightarrow\; (\lambda-1)^2=0 \;\Rightarrow\; \lambda=1 \text{ (duplo)}$$ → **nó impróprio instável**

### Passo 4 — Avaliando em $(-1,1)$

```math
J(-1,1)=\begin{pmatrix}1&2\\1&1\end{pmatrix}
```

$T=1+1=2, D=(1)(1)-(2)(1)=1-2=-1$

Autovalores: $$\lambda^2-2\lambda-1=0 \;\Rightarrow\; \lambda=\frac{2\pm\sqrt{4+4}}{2}=1\pm\sqrt2$$

$D<0$ → **sela** (independente do valor de $T$)

### Conclusão

$$(0,0):\ \textbf{nó impróprio instável} \qquad\qquad (-1,1):\ \textbf{sela}$$




