<h1>Estabilidade - Funções de Lyapunov - 07</h1>

(g) Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 3 & -2 \\ 4 & -1 \end{bmatrix} x
```
---

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{bmatrix}3&4\\-2&-1\end{bmatrix}
```

Calculando $A^TP+PA$ (mesmo procedimento de sempre):

```math
$A^TP+PA=\begin{bmatrix}6p_{11}+8p_{12} & -2p_{11}+2p_{12}+4p_{22}\\ -2p_{11}+2p_{12}+4p_{22} & -4p_{12}-2p_{22}\end{bmatrix}
```

Igualando a $-I$:

$$6p_{11}+8p_{12}=-1 \quad (i)$$
$$-2p_{11}+2p_{12}+4p_{22}=0 \quad (ii)$$
$$-4p_{12}-2p_{22}=-1 \quad (iii)$$

## Passo 2 — resolver o sistema

Da (iii): $p_{22}=\dfrac{1-4p_{12}}{2}=0{,}5-2p_{12}$

Substituindo em (ii):
$$-2p_{11}+2p_{12}+4(0{,}5-2p_{12})=0$$
$$-2p_{11}+2p_{12}+2-8p_{12}=0$$
$$-2p_{11}-6p_{12}=-2 \;\Rightarrow\; p_{11}=1-3p_{12}$$

Substituindo em (i):
$$6(1-3p_{12})+8p_{12}=-1$$
$$6-18p_{12}+8p_{12}=-1$$
$$-10p_{12}=-7 \;\Rightarrow\; p_{12}=0{,}7$$

Logo: $p_{11}=1-3(0{,}7)=1-2{,}1=-1{,}1$

## Passo 3 — checar se $P$ é positiva definida

$$p_{11}=-1{,}1<0$$

**Já falha no primeiro menor principal!** Nem precisa calcular $p_{22}$ ou o determinante — $P$ não é positiva definida.

## Passo 4 — confirmar e classificar via traço e determinante de $A$

$$T=\text{traço}(A)=3+(-1)=2$$
$$D=\det(A)=(3)(-1)-(-2)(4)=-3+8=5$$

$D=5>0$ → autovalores mesmo sinal

$T^2-4D=4-20=-16<0$ → autovalores **complexos** (não reais)

Como $T=2>0$ (parte real positiva) → **foco instável**

## Conclusão

$$P \text{ falhou} \;\Rightarrow\; \text{instável}; \qquad T>0,\ D>0,\ T^2-4D<0 \;\Rightarrow\; \textbf{foco instável}$$

---

Quer seguir para o item (h)?
