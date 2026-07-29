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

## (g): $\dot x=1-y,\quad \dot y=x^2-y^2$

### Passo 1 — Pontos críticos

Da primeira equação: $1-y=0 \Rightarrow y=1$

Substituindo na segunda: $x^2-1^2=0 \Rightarrow x^2=1 \Rightarrow x=\pm1$

**Pontos críticos: $(-1,1)$ e $(1,1)$** ✓ (bate com o gabarito)

### Passo 2 — Jacobiano genérico

$$J(x,y)=\begin{bmatrix}\dfrac{\partial}{\partial x}(1-y) & \dfrac{\partial}{\partial y}(1-y)\\[4pt] \dfrac{\partial}{\partial x}(x^2-y^2) & \dfrac{\partial}{\partial y}(x^2-y^2)\end{bmatrix}=\begin{bmatrix}0&-1\\2x&-2y\end{bmatrix}$$

### Passo 3 — Avaliando em $(-1,1)$

$$J(-1,1)=\begin{bmatrix}0&-1\\-2&-2\end{bmatrix}$$

$$T=0+(-2)=-2,\qquad D=(0)(-2)-(-1)(-2)=0-2=-2$$

$D=-2<0$ → **sela** ✓ (independente de $T$)

### Passo 4 — Avaliando em $(1,1)$

$$J(1,1)=\begin{bmatrix}0&-1\\2&-2\end{bmatrix}$$

$$T=0+(-2)=-2,\qquad D=(0)(-2)-(-1)(2)=0+2=2$$

$D=2>0$; $T^2-4D=4-8=-4<0$ → autovalores **complexos**; $T=-2<0$ → **foco estável**

### Conclusão

$$(-1,1):\ \textbf{sela} \qquad\qquad (1,1):\ \textbf{foco estável}$$
