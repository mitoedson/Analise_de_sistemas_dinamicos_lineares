<h1>Estabilidade - Funções de Lyapunov Quadrática - 13</h1>

Considere o sistema:

```math
\dot x = Ax
```

```math
A = \begin{bmatrix} 0 & 1 \\ -2 & -3 \end{bmatrix} 
```

Construa uma função de Lyapunov quadrática
$V = x^TPx$

usando a equação
$A^TP + PA = −I$

Mostre que P é definida positiva.


---

## Passo 1 — calcular $A^T$

```math
A^T=\begin{bmatrix} 0 & -2 \\  1  & -3\end{bmatrix}
```

## Passo 2 — calcular $A^TP$

```math
A^TP=\begin{bmatrix}0 & -2 \\  1  & -3\end{bmatrix}\begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix}
=\begin{bmatrix} -2p_{12} & -2p_{22} \\ p_{11}-3p_{12} & p_{12}-3p_{22} \end{bmatrix}
```

## Passo 3 — calcular $PA$

```math
PA = \begin{bmatrix}p_{11}&p_{12}\\p_{12}&p_{22}\end{bmatrix} \begin{bmatrix} 0 & 1 \\ -2 & -3 \end{bmatrix} = \begin{bmatrix}-2p_{12} &  p_{11}-3p_{12}\\  -2p_{22} & p_{12}-3p_{22}\end{bmatrix}
```

## Passo 4 — somar $A^TP+PA$

```math
A^TP+PA = \begin{bmatrix} -2p_{12} & -2p_{22} \\ p_{11}-3p_{12} & p_{12}-3p_{22} \end{bmatrix} + \begin{bmatrix}-2p_{12} &  p_{11}-3p_{12}\\  -2p_{22} & p_{12}-3p_{22}\end{bmatrix} = \begin{bmatrix} -4p_{12} & -2p_{22}+p_{11}-3p_{12} \\ -2p_{22}+p_{11}-3p_{12} & 2p_{12}-6p_{22} \end{bmatrix}
```

## Passo 5 — impondo $A^TP+PA=-I$

```math
A^TP+PA = -I \Rightarrow 
\begin{bmatrix} -4p_{12} & -2p_{22}+p_{11}-3p_{12} \\ -2p_{22}+p_{11}-3p_{12} & 2p_{12}-6p_{22} \end{bmatrix} = -\begin{bmatrix} 1 & 0\\ 0 & 1 \end{bmatrix}
```

Temos o sistema:

$$-4p_{12} = - 1 \quad (i)$$
$$-2p_{22}+p_{11}-3p_{12} = 0 \quad (ii)$$ 
$$2p_{12}-6p_{22} = -1 \quad (iii)$$

## Passo 6 — resolver o sistema

De (i): $$p_{12}= \frac{1}{4}$$

De (iii): $$2\frac{1}{4}-6p_{22} = -1 \Rightarrow p_{22} = \frac{1}{4} $$

De (ii): $$-2(\frac{1}{4})+p_{11}-3(\frac{1}{4}) = 0 \Rightarrow p_{11}=\frac{5}{4}$$


## Passo 6 — checar se $P$ é positiva definida
```math
PA = \begin{bmatrix} \frac{5}{4} & \frac{1}{4} \\ \frac{1}{4} & \frac{1}{4}\end{bmatrix}
```
```math
p_{11} = \frac{5}{4} > 0
```
```math
det(P) = (\frac{5}{4})(\frac{1}{4}) - (\frac{1}{4})(\frac{1}{4}) = \frac{5}{16} - \frac{1}{16} = \frac{1}{4} > 0
```

**Falha logo no primeiro menor** → $P$ não é positiva definida → instável.

## Passo 7 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)=2+(-1)=1$$
$$D=\det(A)=(2)(-1)-(-2{,}5)(1{,}8)=-2+4{,}5=2{,}5$$

$D=2{,}5>0$; $T^2-4D=1-10=-9<0$ → autovalores **complexos**; $T=1>0$ → **foco instável**

## Conclusão

$$P \text{ falhou} \;\Rightarrow\; \text{instável}; \qquad T>0,\ D>0,\ T^2-4D<0 \;\Rightarrow\; \textbf{foco instável}$$


