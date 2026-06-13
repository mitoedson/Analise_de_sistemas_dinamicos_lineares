# Autovalores, Autovetores e Estabilidade — Autovalores Repetidos

Para cada sistema $\dot{X} = AX$, determinamos os autovalores $\lambda$ e autovetores $v$ resolvendo $\det(A - \lambda I) = 0$ e $(A - \lambda I)v = 0$. A estabilidade é analisada pelos sinais das partes reais dos autovalores:

| Condição | Classificação |
|---|---|
| $\mathrm{Re}(\lambda) < 0$ para todos | Assintoticamente estável |
| $\mathrm{Re}(\lambda) > 0$ para algum | Instável |
| $\mathrm{Re}(\lambda) \leq 0$ e pelo menos um $= 0$ | Marginalmente estável |

Quando o autovalor repetido possui apenas **um autovetor independente**, a solução geral assume a forma:

$$X(t) = c_1 \, k_1 \, e^{\lambda t} + c_2 \bigl[ k_1 \, t + p \bigr] e^{\lambda t}$$

onde $p$ é o **autovetor generalizado**, obtido de $(A - \lambda I)\,p = k_1$.

---

<b>(a)</b>
<p>
$\frac{dx}{dt} = 3x - y, \qquad \frac{dy}{dt} = 9x - 3y$
$A = [3, -1; 9, -3]$

### Autovalores

$$\det(A - \lambda I) = (3 - \lambda)(-3 - \lambda) + 9 = \lambda^2 = 0$$

$$\boxed{\lambda_{1,2} = 0 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = 0$, resolvemos $A\,v = 0$:

$$[3, -1; 9, -3] \cdot v = 0 \implies 3v_1 = v_2$$

$$\boxed{k_1 = (1; 3)}$$

**Autovetor generalizado** via $A\,p = k_1$:

$$[3, -1; 9, -3] \cdot p = (1; 3)$$

Da primeira linha: $3p_1 - p_2 = 1$. Escolhendo $p_1 = 0 \Rightarrow p_2 = -1$:

$$\boxed{p = (0; -1)}$$

### Solução Geral

$$\boxed{X(t) = c_1\,(1;3) + c_2\,(t;3t-1)}$$

### Estabilidade

$\mathrm{Re}(\lambda) = 0$ — autovalor nulo repetido. As trajetórias crescem linearmente em $t$.

> **Instável** — crescimento polinomial.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/afff4f97-1af2-4149-83dc-3bf929c75e27" />
<p>
**Esquerda — Retrato de fase:** trajetórias no plano $(x_1, x_2)$ partindo de múltiplas condições iniciais. O marcador `+` indica a origem (ponto de equilíbrio). Trajetórias são retas paralelas, pois $e^{0 \cdot t} = 1$ e o crescimento é linear em $t$. As curvas divergem da origem ao longo de uma direção determinada pelo autovetor $k_1 = (1;\,3)$.
<p>
**Direita — Resposta temporal:** evolução de $x_1(t)$ (linha sólida) e $x_2(t)$ (linha tracejada) ao longo do tempo. $x_1(t)$ e $x_2(t)$ crescem **linearmente**, sem oscilação e sem amortecimento exponencial. Trajetórias saem de condições iniciais não nulas e nunca retornam.
<p>
Classificação: Instável — crescimento polinomial (linear).

---

<b>(b)</b>
<p>
$\frac{dx}{dt} = -6x + 5y, \qquad \frac{dy}{dt} = -5x + 4y$
$A = [-6, 5; -5, 4]$

### Autovalores

$$\det(A - \lambda I) = (-6 - \lambda)(4 - \lambda) + 25 = \lambda^2 + 2\lambda + 1 = (\lambda + 1)^2 = 0$$

$$\boxed{\lambda_{1,2} = -1 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = -1$:

$$A + I = [-5, 5; -5, 5] \implies v_1 = v_2$$

$$\boxed{k_1 = (1; 1)}$$

**Autovetor generalizado** via $(A + I)\,p = k_1$:

$$[-5, 5; -5, 5] \cdot p = (1; 1)$$

Da primeira linha: $-5p_1 + 5p_2 = 1$. Escolhendo $p_1 = 0 \Rightarrow p_2 = 1/5$:

$$\boxed{p = (0; 1/5)}$$

### Solução Geral

$$\boxed{X(t) = c_1\,(1;1)\,e^{-t} + c_2\,\bigl[(1;1)\,t + (0;1/5)\bigr]\,e^{-t}}$$

### Estabilidade

$\mathrm{Re}(\lambda) = -1 < 0$ para ambos.

> **Assintoticamente estável** — nó atrator degenerado (estrela imprópria).


## (c)

$$\dot{x} = [-1, 3; -3, 5]\,x$$

$$A = [-1, 3; -3, 5]$$

### Autovalores

$$\det(A - \lambda I) = (-1 - \lambda)(5 - \lambda) + 9 = \lambda^2 - 4\lambda + 4 = (\lambda - 2)^2 = 0$$

$$\boxed{\lambda_{1,2} = 2 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = 2$:

$$A - 2I = [-3, 3; -3, 3] \implies v_1 = v_2$$

$$\boxed{k_1 = (1; 1)}$$

**Autovetor generalizado** via $(A - 2I)\,p = k_1$:

$$[-3, 3; -3, 3] \cdot p = (1; 1)$$

Da primeira linha: $-3p_1 + 3p_2 = 1$. Escolhendo $p_1 = 0 \Rightarrow p_2 = 1/3$:

$$\boxed{p = (0; 1/3)}$$

### Solução Geral

$$\boxed{X(t) = c_1\,(1;1)\,e^{2t} + c_2\,\bigl[(1;1)\,t + (0;1/3)\bigr]\,e^{2t}}$$

### Estabilidade

$\mathrm{Re}(\lambda) = 2 > 0$ para ambos.

> **Instável** — nó repulsor degenerado, trajetórias divergem exponencialmente.

---

## (d)

$$\dot{x} = [12, -9; 4, 0]\,x$$

$$A = [12, -9; 4, 0]$$

### Autovalores

$$\det(A - \lambda I) = (12 - \lambda)(0 - \lambda) + 36 = \lambda^2 - 12\lambda + 36 = (\lambda - 6)^2 = 0$$

$$\boxed{\lambda_{1,2} = 6 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = 6$:

$$A - 6I = [6, -9; 4, -6] \implies 6v_1 = 9v_2 \implies v_1 = \tfrac{3}{2}v_2$$

Escolhendo $v_2 = 2$:

$$\boxed{k_1 = (3; 2)}$$

**Autovetor generalizado** via $(A - 6I)\,p = k_1$:

$$[6, -9; 4, -6] \cdot p = (3; 2)$$

Da segunda linha: $4p_1 - 6p_2 = 2 \Rightarrow 2p_1 - 3p_2 = 1$. Escolhendo $p_2 = 0 \Rightarrow p_1 = 1/2$:

$$\boxed{p = (1/2; 0)}$$

### Solução Geral

$$\boxed{X(t) = c_1\,(3;2)\,e^{6t} + c_2\,\bigl[(3;2)\,t + (1/2;0)\bigr]\,e^{6t}}$$

### Estabilidade

$\mathrm{Re}(\lambda) = 6 > 0$ para ambos.

> **Instável** — nó repulsor degenerado, trajetórias divergem exponencialmente.

---

## Resumo

| Exercício | $A$ | Autovalores | Estabilidade |
|:---------:|:---:|:-----------:|:------------:|
| (a) | $[3,-1;9,-3]$ | $\lambda = 0$ (repet.) | **Instável** (crescimento linear) |
| (b) | $[-6,5;-5,4]$ | $\lambda = -1$ (repet.) | **Assintoticamente estável** |
| (c) | $[-1,3;-3,5]$ | $\lambda = 2$ (repet.) | **Instável** (espiral repulsora) |
| (d) | $[12,-9;4,0]$ | $\lambda = 6$ (repet.) | **Instável** (espiral repulsora) |
