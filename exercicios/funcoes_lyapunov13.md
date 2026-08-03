<h1>Estabilidade - Funções de Lyapunov Quadrática - 13</h1>

Considere o sistema:

```math
\dot x = Ax
```

```math
A= = \begin{bmatrix} 0 & 1 \\ -2 & -3 \end{bmatrix} 
```

Construa uma função de Lyapunov quadrática
$V = x^TPx$

usando a equação
$A^TP + PA = −I$

Mostre que P é definida positiva.


---

Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.

## Passo 1 — calcular $A^T$

```math
A^T=\begin{bmatrix}2&1{,}8\\-2{,}5&-1\end{bmatrix}
```

## Passo 2 — calcular $A^TP$

```math
A^TP=\begin{bmatrix}2&1{,}8\\-2{,}5&-1\end{bmatrix}\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}
```

- (1,1): $2p_{11}+1{,}8p_{12}$
- (1,2): $2p_{12}+1{,}8p_{22}$
- (2,1): $-2{,}5p_{11}-p_{12}$
- (2,2): $-2{,}5p_{12}-p_{22}$

## Passo 3 — calcular $PA$

```math
PA=\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}\begin{bmatrix}2&-2{,}5\\1{,}8&-1\end{bmatrix}
```

- (1,1): $2p_{11}+1{,}8p_{12}$
- (1,2): $-2{,}5p_{11}-p_{12}$
- (2,1): $2p_{12}+1{,}8p_{22}$
- (2,2): $-2{,}5p_{12}-p_{22}$

## Passo 4 — somar $A^TP+PA$

- **(1,1):** $(2p_{11}+1{,}8p_{12})+(2p_{11}+1{,}8p_{12}) = 4p_{11}+3{,}6p_{12}$
- **(1,2):** $(2p_{12}+1{,}8p_{22})+(-2{,}5p_{11}-p_{12}) = -2{,}5p_{11}+p_{12}+1{,}8p_{22}$
- **(2,2):** $(-2{,}5p_{12}-p_{22})+(-2{,}5p_{12}-p_{22}) = -5p_{12}-2p_{22}$

$$A^TP+PA=\begin{bmatrix}4p_{11}+3{,}6p_{12} & -2{,}5p_{11}+p_{12}+1{,}8p_{22}\\ -2{,}5p_{11}+p_{12}+1{,}8p_{22} & -5p_{12}-2p_{22}\end{bmatrix}$$

Igualando a $-I$:

$$4p_{11}+3{,}6p_{12}=-1 \quad (i)$$
$$-2{,}5p_{11}+p_{12}+1{,}8p_{22}=0 \quad (ii)$$
$$-5p_{12}-2p_{22}=-1 \quad (iii)$$

## Passo 5 — resolver o sistema

Da (iii): $p_{22}=0{,}5-2{,}5p_{12}$

Substituindo em (ii):
$$-2{,}5p_{11}+p_{12}+1{,}8(0{,}5-2{,}5p_{12})=0$$
$$-2{,}5p_{11}+p_{12}+0{,}9-4{,}5p_{12}=0$$
$$-2{,}5p_{11}-3{,}5p_{12}=-0{,}9 \;\Rightarrow\; p_{11}=0{,}36-1{,}4p_{12}$$

Substituindo em (i):
$$4(0{,}36-1{,}4p_{12})+3{,}6p_{12}=-1$$
$$1{,}44-5{,}6p_{12}+3{,}6p_{12}=-1$$
$$-2p_{12}=-2{,}44 \;\Rightarrow\; p_{12}=1{,}22$$

Logo: $p_{11}=0{,}36-1{,}4(1{,}22)=0{,}36-1{,}708=-1{,}348$

## Passo 6 — checar se $P$ é positiva definida

$$p_{11}=-1{,}348<0$$

**Falha logo no primeiro menor** → $P$ não é positiva definida → instável.

## Passo 7 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)=2+(-1)=1$$
$$D=\det(A)=(2)(-1)-(-2{,}5)(1{,}8)=-2+4{,}5=2{,}5$$

$D=2{,}5>0$; $T^2-4D=1-10=-9<0$ → autovalores **complexos**; $T=1>0$ → **foco instável**

## Conclusão

$$P \text{ falhou} \;\Rightarrow\; \text{instável}; \qquad T>0,\ D>0,\ T^2-4D<0 \;\Rightarrow\; \textbf{foco instável}$$


