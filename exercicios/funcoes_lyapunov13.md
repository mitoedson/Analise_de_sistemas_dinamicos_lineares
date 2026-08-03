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

Usa-se o critério de Sylvester: os menores principais líderes devem ser positivos.

```math
P = \begin{bmatrix} \frac{5}{4} & \frac{1}{4} \\ \frac{1}{4} & \frac{1}{4}\end{bmatrix}
```
```math
p_{11} = \frac{5}{4} > 0
```
```math
det(P) = (\frac{5}{4})(\frac{1}{4}) - (\frac{1}{4})(\frac{1}{4}) = \frac{5}{16} - \frac{1}{16} = \frac{1}{4} > 0
```
Como $$p_{11} > 0$$ e $$det(P) > 0$$, condições para positiva definida, então P > 0.

## Passo 7 — classificar o tipo via traço e determinante de $A$

$$T=\text{traço}(A)= 0 + (-3) = -3$$
$$D=\det(A)= (0)(-3) - (1)(-2) = 2$$

$$\lambda^2+3\lambda+2=0 \Rightarrow \lambda_1= -1,\lambda_2= -2$$ 

É assintoticamente estável (Nó estável)

## Passo 8 — conclusão por Lyapunov

A função candidata de Lyapunov é $$V(x) = x^TPx$$.

E para isso, 

$$V(x)>0$$ para $$x \ne 0$$ (e $$\quad V(0)=0$$) — candidata precisa ser "tipo energia"

$$\dot 𝑉 (x) < 0$$ para $$x \ne 0$$ -  a "energia" precisa estar sempre decrescendo

Como P > 0, e é aplicada a V(x), então V(x) > 0 para $$x \ne 0$$.

Além disso, como $$V(x) = x^TPx$$, e $$\dot V = \frac{d}{dt}(x^TPx) = \dot x^T Px + x^TP\dot x \quad\text{(regra da cadeia, regra do produto)}$$

e $$\dot x = Ax$$, $$\dot V = (Ax)^T Px + x^TP(Ax) \Rightarrow V = x^TA^T Px + x^TP(Ax) = x^T(A^TP+PA)x$$ 

Como $$A^TP + PA = −I$$, segue que:
```math
\dot V = x^(-I)x = -\begin{bmatrix} x_1 & x_2 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} \Rightarrow \dot V = -(x_1^2+x_2^2) < 0
```

Assim, 

Logo, a origem é assintoticamente estável.

---

<a href="funcoes_lyapunov_metodo.md">Método Sistemático da Função de Lyapunov</a>

Usando o fluxo: equação de Lyapunov (com $Q=I$) → checar $P$ pelos menores principais líderes → confirmar/classificar o tipo via $T$ e $D$ de $A$.
