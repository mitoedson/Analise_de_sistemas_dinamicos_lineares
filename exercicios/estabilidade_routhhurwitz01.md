<h1>Estabilidade - Critério de Routh-Hurwitz - 01</h1>

### Determine os valores da constante k para que todas as raízes dos seguintes polinômios tenham parte real negativa:

### (a) λ³ + kλ² + λ + 1 = 0

Coeficientes: $a_0=1,\ a_1=k,\ a_2=1,\ a_3=1$

| | col 1 | col 2 |
|---|---|---|
|λ³| 1 | 1 |
|λ²| k | 1 |
|λ¹| $\dfrac{k\cdot1-1\cdot1}{k}=\dfrac{k-1}{k}$ | |
|λ⁰| 1 | |

Precisamos de $k>0$ **e** $\dfrac{k-1}{k}>0$. Como $k>0$, isso exige $k-1>0$.

**Resultado: $k>1$** ✓ (bate com o gabarito)

## (b) λ³ + λ² + λ + k = 0

Coeficientes: $a_0=1,\ a_1=1,\ a_2=1,\ a_3=k$

| | col 1 | col 2 |
|---|---|---|
|λ³| 1 | 1 |
|λ²| 1 | k |
|λ¹| $\dfrac{1\cdot1-1\cdot k}{1}=1-k$ | |
|λ⁰| k | |

Precisamos de $1-k>0 \Rightarrow k<1$ e $k>0$.

**Resultado: $0<k<1$** ✓

## (c) λ⁴ + kλ³ + λ² + λ + 1 = 0

Coeficientes: $a_0=1,\ a_1=k,\ a_2=1,\ a_3=1,\ a_4=1$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $b_1=\dfrac{k\cdot1-1\cdot1}{k}=\dfrac{k-1}{k}$ | $b_2=1$ | |
|λ¹| $c_1=\dfrac{b_1\cdot1-k\cdot b_2}{b_1}$ | | |
|λ⁰| 1 | | |

Para ter $b_1>0$ com $k>0$, precisamos $k>1$.

Calculando $c_1$:
$$c_1=\frac{\frac{k-1}{k}-k}{\frac{k-1}{k}}=\frac{k-1-k^2}{k-1}=-\frac{k^2-k+1}{k-1}$$

O discriminante de $k^2-k+1$ é $1-4=-3<0$, então $k^2-k+1>0$ **sempre**. Como já exigimos $k>1$ (logo $k-1>0$), temos $c_1=-\dfrac{(+)}{(+)}<0$ **sempre**.

Ou seja, é impossível ter $b_1>0$ e $c_1>0$ ao mesmo tempo.

**Resultado: não existe $k\in\mathbb{R}$** ✓

## (d) λ⁴ + λ³ + λ² + λ + k = 0

Coeficientes: $a_0=1,\ a_1=1,\ a_2=1,\ a_3=1,\ a_4=k$

| | col 1 | col 2 |
|---|---|---|
|λ⁴| 1 | 1 |
|λ³| 1 | 1 |
|λ²| $\dfrac{1\cdot1-1\cdot1}{1}=0$ | $k$ |

Já na linha λ² aparece **0 na primeira coluna**, independentemente de $k$. Isso por si só impede estabilidade estrita (sinaliza raízes sobre o eixo imaginário ou problema na construção do array).

**Resultado: não existe $k\in\mathbb{R}$** ✓

## (e) λ⁵ + λ⁴ + kλ³ + λ² + λ + k = 0

Coeficientes: $a_0=1,\ a_1=1,\ a_2=k,\ a_3=1,\ a_4=1,\ a_5=k$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| $b_1=k-1$ | $b_2=1-k$ | 0 |
|λ²| $c_1=2$ | $c_2=k$ | |
|λ¹| $d_1$ | | |
|λ⁰| $k$ | | |

Detalhe do cálculo de $c_1$:
$$c_1=\frac{(k-1)(1)-1\cdot(1-k)}{k-1}=\frac{(k-1)+(k-1)}{k-1}=2$$

Detalhe de $d_1$:
$$d_1=\frac{c_1 b_2-b_1c_2}{c_1}=\frac{2(1-k)-(k-1)k}{2}=\frac{2-2k-k^2+k}{2}=-\frac{(k+2)(k-1)}{2}$$

Exigências: $k-1>0\Rightarrow k>1$, e $d_1>0$.

Mas para $k>1$: $(k+2)>0$ e $(k-1)>0$, logo $(k+2)(k-1)>0$, então $d_1=-\dfrac{(+)}{2}<0$ **sempre**.

**Resultado: não existe $k\in\mathbb{R}$** ✓

