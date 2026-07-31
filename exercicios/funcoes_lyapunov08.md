<h1>Estabilidade - Funções de Lyapunov - 08</h1>

(h) Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} -1 & -1 \\ 0 & -0,25 \end{bmatrix} x
```
---

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{bmatrix}-1&0\\-1&-0{,}25\end{bmatrix}
```

Calculando $A^TP+PA$:

```math
A^TP+PA=\begin{bmatrix}-2p_{11} & -p_{11}-1{,}25p_{12}\\ -p_{11}-1{,}25p_{12} & -2p_{12}-0{,}5p_{22}\end{bmatrix}
```

Igualando a $-I$:

$$-2p_{11}=-1 \quad (i)$$
$$-p_{11}-1{,}25p_{12}=0 \quad (ii)$$
$$-2p_{12}-0{,}5p_{22}=-1 \quad (iii)$$

## Passo 2 — resolver o sistema

Da (i): $p_{11}=0{,}5$

Substituindo em (ii): $-0{,}5-1{,}25p_{12}=0 \Rightarrow p_{12}=-0{,}4$

Substituindo em (iii): $-2(-0{,}4)-0{,}5p_{22}=-1 \Rightarrow 0{,}8-0{,}5p_{22}=-1 \Rightarrow p_{22}=3{,}6$

## Passo 3 — checar se $P$ é positiva definida

$$P=\begin{bmatrix}0{,}5&-0{,}4\\-0{,}4&3{,}6\end{bmatrix}$$

**Menor 1:** $p_{11}=0{,}5>0$ ✓

**Menor 2 (determinante):** $\det(P)=(0{,}5)(3{,}6)-(-0{,}4)^2=1{,}8-0{,}16=1{,}64>0$ ✓

**$P$ é positiva definida!** → **assintoticamente estável**

## Passo 4 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)=-1+(-0{,}25)=-1{,}25$$
$$D=\det(A)=(-1)(-0{,}25)-(-1)(0)=0{,}25$$

$D=0{,}25>0$; $T^2-4D=1{,}5625-1=0{,}5625>0$ (autovalores reais); $T<0$ → **nó estável**

## Conclusão

$$P>0 \Rightarrow \text{assintoticamente estável}; \qquad T<0,\ D>0,\ T^2-4D>0 \;\Rightarrow\; \textbf{nó estável}$$


