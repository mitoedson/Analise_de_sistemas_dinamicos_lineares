<h1>Estabilidade - Funções de Lyapunov - 06</h1>

(f) Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 2 & -5 \\ 1 & -2 \end{bmatrix} x
```
---

## Passo 1 — montar a equação de Lyapunov com $Q=I$

$$A^T=\begin{bmatrix}2&1\\-5&-2\end{bmatrix}$$

Calculando $A^TP$:
$$A^TP=\begin{bmatrix}2&1\\-5&-2\end{bmatrix}\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}=\begin{bmatrix}2p_{11}+p_{12} & 2p_{12}+p_{22}\\-5p_{11}-2p_{12} & -5p_{12}-2p_{22}\end{bmatrix}$$

$PA$ é a transposta disso (já que $P$ é simétrica):
$$PA=\begin{bmatrix}2p_{11}+p_{12} & -5p_{11}-2p_{12}\\2p_{12}+p_{22} & -5p_{12}-2p_{22}\end{bmatrix}$$

Somando:
$$A^TP+PA=\begin{bmatrix}4p_{11}+2p_{12} & -5p_{11}+p_{22}\\ -5p_{11}+p_{22} & -10p_{12}-4p_{22}\end{bmatrix}$$

Igualando a $-I$:

$$4p_{11}+2p_{12}=-1 \quad (i)$$
$$-5p_{11}+p_{22}=0 \quad (ii)$$
$$-10p_{12}-4p_{22}=-1 \quad (iii)$$

## Passo 2 — resolver o sistema

Da (ii): $p_{22}=5p_{11}$

Da (i): $p_{12}=\dfrac{-1-4p_{11}}{2}$

Substituindo em (iii):
$$-10\left(\frac{-1-4p_{11}}{2}\right)-4(5p_{11})=-1$$
$$5(1+4p_{11})-20p_{11}=-1$$
$$5+20p_{11}-20p_{11}=-1$$
$$5=-1$$

## Contradição! Não existe solução para $P$

Assim como no item (c), a equação de Lyapunov **não tem solução** para $Q=I$.

## Confirmando via traço e determinante de $A$

$$T=\text{traço}(A)=2+(-2)=0$$
$$D=\det(A)=(2)(-2)-(-5)(1)=-4+5=1$$

De novo, $T=0$ — a mesma condição de "ressonância" que vimos no item (c) (autovalores somam zero, causando a equação de Lyapunov sem solução).

Como $D=1>0$ e $T=0$: caímos exatamente no caso **centro** (autovalores imaginários puros, $\lambda=\pm i\sqrt{D}$, já que $T^2-4D=0-4=-4<0$, complexos, e parte real $=T/2=0$).

## Conclusão

$$T=0,\ D>0 \;\Rightarrow\; \textbf{centro} \;\Rightarrow\; \text{estável, mas não assintoticamente estável}$$

