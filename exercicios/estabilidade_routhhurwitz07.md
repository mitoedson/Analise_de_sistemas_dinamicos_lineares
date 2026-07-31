<h1>Estabilidade - Critério de Routh-Hurwitz - 07</h1>

Analise a estabilidade do seguinte polinômio:

$λ^5 + 3λ^4 + 8λ^3 + 40λ^2 + 68λ + 60 = 0$

utilizando o critério de Routh. Quantas raízes do polinômio tem parte real positiva?

---

Coeficientes: $a_0=1,\ a_1=3,\ a_2=8,\ a_3=40,\ a_4=68,\ a_5=60$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$λ^5$| 1 | 8 | 68 |
|$λ^4$| 3 | 40 | 60 |
|$λ^3$| $b_1$ | $b_2$ | |
|$λ^2$| $c_1$ | $c_2$ | |
|$λ^1$| $d_1$ | $d_2$ | |
|$λ^0$| $e_1$ | | |

```math
b_1 = -\frac{\begin{bmatrix} 1 & 8 \\ 3 & 40 \end{bmatrix}}{3} = -\frac{16}{3}, 
b_2 = -\frac{\begin{bmatrix} 1 & 68 \\ 3 & 60 \end{bmatrix}}{3} = 48
```
```math
c_1 = -\frac{\begin{bmatrix} 3 & 40 \\ -\frac{16}{3} & 48 \end{bmatrix}}{-\frac{16}{3}} = 67, 
c_2 = -\frac{\begin{bmatrix} 3 & 60 \\ -\frac{16}{3} & 0 \end{bmatrix}}{-\frac{16}{3}} = 60
```
```math
d_1 = -\frac{\begin{bmatrix} -\frac{16}{3} & 48 \\ 67 & 60 \end{bmatrix}}{67} = \frac{3536}{67}, 
d_2 = 0
```
```math
e_1 = -\frac{\begin{bmatrix} 67 & 60 \\ \frac{3536}{67} & 0 \end{bmatrix}}{\frac{3536}{67}} = 60 
```


| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$λ^5$| 1 | 8 | 68 |
|$λ^4$| 3 | 40 | 60 |
|$λ^3$| $-\frac{16}{3}$ (primeira troca de sinal)| 48 | 0 |
|$λ^2$| 67 (segunda troca de sinal)| 60 | 0 |
|$λ^1$| $\frac{3536}{67}$ | 0 | |
|$λ^0$| 60 | | |


Boa observação sobre as trocas de sinal — mas vale corrigir a terminologia, porque aqui estamos falando de **raízes de um polinômio** (não de pontos críticos de um sistema não linear, que é um conceito diferente, da questão 2). Vamos montar o array completo e confirmar sua contagem.

## Montando o array de Routh

Polinômio: $\lambda^5+3\lambda^4+8\lambda^3+40\lambda^2+68\lambda+60=0$

Coeficientes: $a_0=1,\ a_1=3,\ a_2=8,\ a_3=40,\ a_4=68,\ a_5=60$

| | col 1 | col 2 | col 3 |
|---|---|---|---|
|$\lambda^5$| 1 | 8 | 68 |
|$\lambda^4$| 3 | 40 | 60 |

## Calculando a linha $\lambda^3$

$$b_1=\frac{(3)(8)-(1)(40)}{3}=\frac{24-40}{3}=-\frac{16}{3}$$
$$b_2=\frac{(3)(68)-(1)(60)}{3}=\frac{204-60}{3}=48$$

## Calculando a linha $\lambda^2$

$$c_1=\frac{\left(-\frac{16}{3}\right)(40)-(3)(48)}{-\frac{16}{3}}=\frac{-\frac{640}{3}-144}{-\frac{16}{3}}=\frac{-\frac{1072}{3}}{-\frac{16}{3}}=\frac{1072}{16}=67$$

$$c_2=\frac{\left(-\frac{16}{3}\right)(60)-(3)(0)}{-\frac{16}{3}}=\frac{-320}{-\frac{16}{3}}=60$$

## Calculando a linha $\lambda^1$

$$d_1=\frac{(67)(48)-\left(-\frac{16}{3}\right)(60)}{67}=\frac{3216+320}{67}=\frac{3536}{67}\approx52{,}78$$

## Calculando a linha $\lambda^0$

$$e_1=60 \quad \text{(último coeficiente)}$$

## Montando a coluna 1 completa

$$1,\quad 3,\quad -\frac{16}{3},\quad 67,\quad 52{,}78,\quad 60$$

## Contando as trocas de sinal

$$\underbrace{1}_{+} \to \underbrace{3}_{+} \to \underbrace{-\frac{16}{3}}_{-} \to \underbrace{67}_{+} \to \underbrace{52{,}78}_{+} \to \underbrace{60}_{+}$$

- $+\to+$: sem troca
- $+\to-$: **1ª troca**
- $-\to+$: **2ª troca**
- $+\to+$: sem troca
- $+\to+$: sem troca

**Total: 2 trocas de sinal** — confirma sua contagem! ✓

O critério de Routh-Hurwitz diz:

 **O número de trocas de sinal na primeira coluna = número de raízes com parte real positiva**

**2 raízes do polinômio têm parte real positiva** 
Como há raízes com parte real positiva, o sistema associado a esse polinômio (se fosse um polinômio característico de um sistema linear) seria **instável**.

