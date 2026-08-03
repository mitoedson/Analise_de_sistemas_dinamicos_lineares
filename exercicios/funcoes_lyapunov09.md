<h1>Funções de Lyapunov - 09</h1>

Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 3 & -4 \\ 1 & -1 \end{bmatrix} x
```
---

## Passo 1 — montar a equação de Lyapunov com $Q=I$

```math
A^T=\begin{bmatrix}3&1\\-4&-1\end{bmatrix}
```

Calculando $A^TP+PA$:

```math
A^TP+PA=\begin{bmatrix}6p_{11}+2p_{12} & -4p_{11}+2p_{12}+p_{22}\\ -4p_{11}+2p_{12}+p_{22} & -8p_{12}-2p_{22}\end{bmatrix}
```

Igualando a $-I$:

$$6p_{11}+2p_{12}=-1 \quad (i)$$
$$-4p_{11}+2p_{12}+p_{22}=0 \quad (ii)$$
$$-8p_{12}-2p_{22}=-1 \quad (iii)$$

## Passo 2 — resolver o sistema

Da (iii): $p_{22}=\dfrac{1-8p_{12}}{2}=0{,}5-4p_{12}$

Substituindo em (ii):
$$-4p_{11}+2p_{12}+0{,}5-4p_{12}=0 \;\Rightarrow\; -4p_{11}-2p_{12}=-0{,}5 \;\Rightarrow\; p_{11}=0{,}125-0{,}5p_{12}$$

Substituindo em (i):
$$6(0{,}125-0{,}5p_{12})+2p_{12}=-1$$
$$0{,}75-3p_{12}+2p_{12}=-1$$
$$-p_{12}=-1{,}75 \;\Rightarrow\; p_{12}=1{,}75$$

Logo: $p_{11}=0{,}125-0{,}5(1{,}75)=0{,}125-0{,}875=-0{,}75$

## Passo 3 — checar se $P$ é positiva definida

$$p_{11}=-0{,}75<0$$

**Falha logo no primeiro menor** → $P$ não é positiva definida → instável.

## Passo 4 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)=3+(-1)=2$$
$$D=\det(A)=(3)(-1)-(-4)(1)=-3+4=1$$

$D=1>0$; $T^2-4D=4-4=0$ → autovalores reais e **repetidos** ($\lambda=T/2=1$); $T>0$ → **nó instável (degenerado)**

## Conclusão

$$P \text{ falhou} \;\Rightarrow\; \text{instável}; \qquad T>0,\ D>0,\ T^2-4D=0 \;\Rightarrow\; \textbf{nó instável}$$

---

<a href="funcoes_lyapunov_metodo.md">Método Sistemático da Função de Lyapunov</a>

Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.


