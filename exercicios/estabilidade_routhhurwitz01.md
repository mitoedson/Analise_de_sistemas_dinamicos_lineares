<h1>Estabilidade - Critério de Routh-Hurwitz - 01</h1>

### Método geral

Dado um polinômio característico

$$a_n s^n + a_{n-1}s^{n-1} + \dots + a_1 s + a_0 = 0$$

você monta a tabela de Routh-Hurwitz (as linhas $s^n, s^{n-1}, \dots, s^0$) e o critério diz:

- **Todos os elementos da primeira coluna devem ter o mesmo sinal** (sem mudança de sinal) para que o sistema seja estável (todas as raízes no semiplano esquerdo).
- **O número de mudanças de sinal na primeira coluna é igual ao número de raízes no semiplano direito** (instáveis).

Ou seja, não é só "verificar se não muda de sinal" — a contagem de trocas de sinal também te dá quantos polos instáveis existem, o que é útil mesmo quando o sistema já é sabidamente instável e você quer saber "quão instável".

**Duas condições necessárias antes de montar a tabela** (teste rápido, evita trabalho desnecessário):
1. Todos os coeficientes $a_i$ devem existir (nenhum estar ausente/zero).
2. Todos os coeficientes devem ter o mesmo sinal.

Se qualquer uma dessas falhar, o sistema já é instável e nem precisa montar a tabela completa.

**Casos especiais** (que costumam pegar todo mundo de surpresa):
- **Zero na primeira coluna** (mas não a linha inteira): substitui-se por $\epsilon \to 0^+$ e continua o cálculo, analisando o sinal no limite.
- **Linha inteira de zeros**: indica raízes simétricas em relação à origem (par imaginário puro, ou par real simétrico). Nesse caso usa-se o "polinômio auxiliar" da linha anterior, deriva-se, e substitui-se a linha de zeros pelos coeficientes da derivada.

### Montagem da tabela

Para $a_n s^n + a_{n-1}s^{n-1} + \dots + a_0$:

| $s^n$ | $a_n$ | $a_{n-2}$ | $a_{n-4}$ | ... |
|---|---|---|---|---|
| $s^{n-1}$ | $a_{n-1}$ | $a_{n-3}$ | $a_{n-5}$ | ... |
| $s^{n-2}$ | $b_1$ | $b_2$ | $b_3$ | ... |
| $s^{n-3}$ | $c_1$ | $c_2$ | ... | |
| $\vdots$ | | | | |
| $s^0$ | ... | | | |

As duas primeiras linhas vêm direto dos coeficientes (ímpares numa linha, pares na outra). A partir da terceira linha em diante, cada elemento é calculado por um determinante cruzado dividido pelo elemento da linha imediatamente acima na primeira coluna:

$$b_1 = \frac{a_{n-1}a_{n-2} - a_n a_{n-3}}{a_{n-1}}, \quad b_2 = \frac{a_{n-1}a_{n-4} - a_n a_{n-5}}{a_{n-1}}$$

e assim por diante, sempre usando as duas linhas anteriores.

**Dica prática:** monte com bastante cuidado nas primeiras vezes — é fácil trocar sinal no determinante cruzado ($a_{n-1}a_{n-2} - a_n a_{n-3}$, não o contrário). Se quiser, me manda um polinômio de exemplo que eu monto a tabela passo a passo com você, ou se preferir eu posso te dar um exercício pra você tentar e eu confiro o resultado.

---

## Determine os valores da constante k para que todas as raízes dos seguintes polinômios tenham parte real negativa:

### (a) λ³ + kλ² + λ + 1 = 0

Pelo critério de Routh:

Coeficientes: $a_0=1,\ a_1=k,\ a_2=1,\ a_3=1$

| | col 1 | col 2 | col 3|
|---|---|---|---|
|λ³| 1 | 1 | 0 |
|λ²| k | 1 | 0 |
|λ¹| $b_1$ | $b_2$ | |
|λ⁰| $c_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 1 \\ k & 1 \end{bmatrix}}{k} = -\frac{1-k}{k}, 
b_2 = -\frac{\begin{bmatrix} 1 & 1 \\ 0 & 0 \end{bmatrix}}{k} = 0
```

| | col 1 | col 2 | col 3|
|---|---|---|---|
|λ³| 1 | 1 | 0 |
|λ²| k | 1 | 0 |
|λ¹| $-\frac{1-k}{k}$ | 0 | |
|λ⁰| $c_1$ | | |


```math
c_1 = -\frac{\begin{bmatrix} k & 1 \\ -\frac{1-k}{k} & 0 \end{bmatrix}}{-\frac{1-k}{k}} = -\frac{\frac{1-k}{k}}{-\frac{1-k}{k}}=1
```

| | col 1 | col 2 |
|---|---|---|
|λ³| 1 | 1 |
|λ²| k | 1 |
|λ¹| $\dfrac{k-1}{k}$ | 0 |
|λ⁰| 1 | |

Precisamos de $k>0$ **e** $\dfrac{k-1}{k}>0$. Como $k>0$, isso exige $k-1>0$.

Portanto, $k>1$

---

## (b) λ³ + λ² + λ + k = 0

Pelo critério de Routh:

Coeficientes: $a_0=1,\ a_1=1,\ a_2=1,\ a_3=k$

| | col 1 | col 2 | col 3|
|---|---|---|---|
|λ³| 1 | 1 | 0 |
|λ²| 1 | k | 0 |
|λ¹| $b_1$ | $b_2$ | |
|λ⁰| $c_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & k \end{bmatrix}}{1} = -\frac{k-1}{1} = -k+1, 
b_2 = -\frac{\begin{bmatrix} 1 & 0 \\ 1 & 0 \end{bmatrix}}{1} = 0
```

| | col 1 | col 2 | col 3|
|---|---|---|---|
|λ³| 1 | 1 | 0 |
|λ²| 1 | k | 0 |
|λ¹| -k+1 | 0 | |
|λ⁰| $c_1$ | | |


```math
c_1 = -\frac{\begin{bmatrix} 1 & k \\ -k+1 & 0 \end{bmatrix}}{-k+1} = -\frac{0-(-k^2+k)}{-k+1} = -\frac{-k(-k+1)}{-k+1} = k
```

| | col 1 | col 2 |
|---|---|---|
|λ³| 1 | 1 |
|λ²| k | 1 |
|λ¹| -k+1 | 0 |
|λ⁰| k | |

Precisamos de $1-k>0 \Rightarrow k<1$ e $k>0$.

Portanto, $0<k<1$

---

## (c) λ⁴ + kλ³ + λ² + λ + 1 = 0

Coeficientes: $a_0=1,\ a_1=k,\ a_2=1,\ a_3=1,\ a_4=1$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $b_1$ | $b_2$ | |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 1 \\ k & 1 \end{bmatrix}}{k} = -\frac{1-k}{k} = \frac{k-1}{k}, 
b_2 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix}}{k} = -\frac{-k}{k} = 1
```


| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $\frac{k-1}{k}$ | 1 | 0 |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |


```math
c_1 = -\frac{\begin{bmatrix} k & 1 \\ \frac{k-1}{k} & 1 \end{bmatrix}}{\frac{k-1}{k}} = -\frac{k-(\frac{k-1}{k})}{\frac{k-1}{k}} = -\frac{k^2-k+1}{k-1}, 
c_2 = -\frac{\begin{bmatrix} k & 0 \\ \frac{k-1}{k} & 0 \end{bmatrix}}{\frac{k-1}{k}} = -\frac{0}{\frac{k-1}{k}} = 0
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $\frac{k-1}{k}$ | 1 | 0 |
|λ¹| $-\frac{k^2-k+1}{k-1}$ | 0 | |
|λ⁰| $d_1$ | | |

```math
d_1 = -\frac{\begin{bmatrix} \frac{k-1}{k} & 1 \\ -\frac{k^2-k+1}{k-1} & 0 \end{bmatrix}}{-\frac{k^2-k+1}{k-1}} = 1
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | 1 |
|λ³| k | 1 | 0 |
|λ²| $\frac{k-1}{k}$ | 1 | 0 |
|λ¹| $-\frac{k^2-k+1}{k-1}$ | 0 | |
|λ⁰| 1 | | |

Precisamos de $k-1>0 \Rightarrow k>1$, e $-k^2+k-1>0 \Rightarrow$ não possui raízes em k, logo $-k^2+k-1 < 0$ para todo k Real.

Portanto, não existe $k\in\mathbb{R}$

---

## (d) λ⁴ + λ³ + λ² + λ + k = 0

Coeficientes: $a_0=1,\ a_1=1,\ a_2=1,\ a_3=1,\ a_4=k$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | k |
|λ³| 1 | 1 | 0 |
|λ²| $b_1$ | $b_2$ | |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & 1 \end{bmatrix}}{1} = -\frac{0}{1} = 0, 
b_2 = -\frac{\begin{bmatrix} 1 & k \\ 1 & 0 \end{bmatrix}}{1} = -\frac{-k}{1} = k
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁴| 1 | 1 | k |
|λ³| 1 | 1 | 0 |
|λ²| 0 | k | |
|λ¹| $c_1$ | $c_2$ | |
|λ⁰| $d_1$ | | |


Já na linha λ² aparece **0 na primeira coluna**, independentemente de $k$. Isso por si só impede estabilidade estrita (sinaliza raízes sobre o eixo imaginário ou problema na construção do array).

Portanto, não existe $k\in\mathbb{R}$

---

## (e) λ⁵ + λ⁴ + kλ³ + λ² + λ + k = 0

Coeficientes: $a_0=1,\ a_1=1,\ a_2=k,\ a_3=1,\ a_4=1,\ a_5=k$


| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| $b_1$ | $b_2$ | |
|λ²| $c_1$ | $c_2$ | |
|λ¹| $d_1$ | $d_1$ | |
|λ⁰| $e_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & k \\ 1 & 1 \end{bmatrix}}{1} = -\frac{1-k}{1} = k-1, 
b_2 = -\frac{\begin{bmatrix} 1 & 1 \\ 1 & k \end{bmatrix}}{1} = -\frac{k-1}{1} = -k+1 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| $c_1$ | $c_2$ | |
|λ¹| $d_1$ | $d_1$ | |
|λ⁰| $e_1$ | | |

```math
c_1 = -\frac{\begin{bmatrix} 1 & 1 \\ k-1 & -k+1 \end{bmatrix}}{k-1} = -\frac{-k+1-(k-1))}{k-1} = 2, 
c_2 = -\frac{\begin{bmatrix} 1 & k \\ k-1 & 0 \end{bmatrix}}{k-1} = -\frac{-k^2+k}{k-1} = k 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| 2 | k | 0 |
|λ¹| $d_1$ | $d_1$ | |
|λ⁰| $e_1$ | | |


```math
d_1 = -\frac{\begin{bmatrix} k-1 & -k+1 \\ 2 & k \end{bmatrix}}{2} = -\frac{k^2+k-2}{2}, 
d_2 = -\frac{\begin{bmatrix} k-1 & 0 \\ 2 & 0 \end{bmatrix}}{2} = -\frac{0}{2} = 0 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| 2 | k | 0 |
|λ¹| $-\frac{k^2+k-2}{2}$ | 0 | |
|λ⁰| $e_1$ | | |

```math
e_1 = -\frac{\begin{bmatrix} 2 & k \\ -\frac{k^2+k-2}{2} & 0 \end{bmatrix}}{-\frac{k^2+k-2}{2}} = -\frac{k\frac{k^2+k-2}{2}}{-\frac{k^2+k-2}{2}} = k 
```

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|λ⁵| 1 | k | 1 |
|λ⁴| 1 | 1 | k |
|λ³| k-1 | -k+1 | 0 |
|λ²| 2 | k | 0 |
|λ¹| $-\frac{k^2+k-2}{2}$ | 0 | |
|λ⁰| k | | |

Precisamos de $k-1>0 \Rightarrow k>1$, k>0, e $-\frac{k^2+k-2}{2} \Rightarrow -k^2-k+2 > 0$. Porém, $-k^2-k+2 > 0$, se e somente se, -2 < k < 1. 

Portanto, não existe $k\in\mathbb{R}$

