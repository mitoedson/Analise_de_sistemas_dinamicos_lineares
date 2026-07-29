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

Sim, exatamente o mesmo procedimento! E até já fizemos a parte 1 (pontos críticos) desse item lá atrás, como exemplo de fatoração — vou recapitular rapidinho e depois ir para a classificação.

## (f): $\dot x=x-x^2-xy,\quad \dot y=3y-xy-2y^2$

## Passo 1 — Pontos críticos (já feito antes)

Fatorando:
$$\dot x = x(1-x-y)=0 \;\Rightarrow\; x=0 \text{ ou } 1-x-y=0$$
$$\dot y = y(3-x-2y)=0 \;\Rightarrow\; y=0 \text{ ou } 3-x-2y=0$$

Combinando os casos (2×2=4), obtivemos:
$$(0,0),\quad (0,\,3/2),\quad (1,\,0),\quad (-1,\,2)$$

## Passo 2 — Jacobiano genérico

$$J(x,y)=\begin{bmatrix} 1-2x-y & -x \\ -y & 3-x-4y \end{bmatrix}$$

## Passo 3 — Avaliar em cada ponto (T, D, classificação)

**Em $(0,0)$:**
$$J=\begin{bmatrix}1&0\\0&3\end{bmatrix} \Rightarrow T=4,\ D=3$$
$D>0$, $T^2-4D=16-12=4>0$ (reais), $T>0$ → **nó instável** ✓

**Em $(0, 3/2)$:**
$$J=\begin{bmatrix}1-3/2 & 0\\ -3/2 & 3-6\end{bmatrix}=\begin{bmatrix}-1/2&0\\-3/2&-3\end{bmatrix} \Rightarrow T=-\tfrac72,\ D=\tfrac32$$
$D>0$, $T^2-4D=\tfrac{49}{4}-6=\tfrac{25}{4}>0$ (reais), $T<0$ → **nó estável** ✓

**Em $(1,0)$:**
$$J=\begin{bmatrix}1-2&-1\\0&3-1\end{bmatrix}=\begin{bmatrix}-1&-1\\0&2\end{bmatrix} \Rightarrow T=1,\ D=-2$$
$D<0$ → **sela** ✓

**Em $(-1,2)$:**
$$J=\begin{bmatrix}1+2-2&1\\-2&3+1-8\end{bmatrix}=\begin{bmatrix}1&1\\-2&-4\end{bmatrix} \Rightarrow T=-3,\ D=-4+2=-2$$
$D<0$ → **sela** ✓

## Conclusão

$(0,0)$ nó instável; $(0,3/2)$ nó estável; $(1,0)$ sela; $(-1,2)$ sela

