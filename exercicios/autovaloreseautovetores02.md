# Autovalores, Autovetores e Estabilidade

Para cada sistema $\dot{X} = AX$, determinamos os autovalores $\lambda$ e autovetores $v$ resolvendo $\det(A - \lambda I) = 0$ e $(A - \lambda I)v = 0$. A estabilidade é analisada pelos sinais das partes reais dos autovalores:

| Condição | Classificação |
|---|---|
| $\mathrm{Re}(\lambda) < 0$ para todos | Assintoticamente estável |
| $\mathrm{Re}(\lambda) > 0$ para algum | Instável |
| $\mathrm{Re}(\lambda) \leq 0$ e pelo menos um $= 0$ | Marginalmente estável |

---

## (a)

$\frac{dx}{dt} = 3x - y, \qquad \frac{dy}{dt} = 9x - 3y$
<p>
$A = \begin{bmatrix} 3 & -1 \\ 9 & -3 \end{bmatrix}$
</p>
### Autovalores

$$\det(A - \lambda I) = (3 - \lambda)(-3 - \lambda) + 9 = \lambda^2 - 9 + 9 = \lambda^2 = 0$$

$$\boxed{\lambda_{1,2} = 0 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = 0$, resolvemos $(A - 0 \cdot I)v = 0$:

$$\begin{bmatrix} 3 & -1 \\ 9 & -3 \end{bmatrix} v = 0 \implies 3v_1 = v_2$$

$$\boxed{k_1 = \begin{pmatrix} 1 \\ 3 \end{pmatrix}}$$

Como o autovalor é repetido com apenas **um autovetor independente**, buscamos o **autovetor generalizado** $p$ via $(A - \lambda I)p = k_1$:

$$\begin{bmatrix} 3 & -1 \\ 9 & -3 \end{bmatrix} \begin{pmatrix} p_1 \\ p_2 \end{pmatrix} = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$$

Da primeira linha: $3p_1 - p_2 = 1$. Escolhendo $p_1 = 0 \Rightarrow p_2 = -1$:

$$\boxed{p = \begin{pmatrix} 0 \\ -1 \end{pmatrix}}$$

### Solução Geral

$$X(t) = c_1 \begin{pmatrix} 1 \\ 3 \end{pmatrix} e^{0 \cdot t} + c_2 \left[ \begin{pmatrix} 1 \\ 3 \end{pmatrix} t + \begin{pmatrix} 0 \\ -1 \end{pmatrix} \right] e^{0 \cdot t}$$

$$\boxed{X(t) = c_1 \begin{pmatrix} 1 \\ 3 \end{pmatrix} + c_2 \begin{pmatrix} t \\ 3t - 1 \end{pmatrix}}$$

### Estabilidade

$\mathrm{Re}(\lambda) = 0$ (autovalor nulo repetido). As trajetórias crescem linearmente em $t$.

> **Instável** — autovalor nulo repetido com autovetor generalizado provoca crescimento polinomial.

---

## (b)

$$\frac{dx}{dt} = -6x + 5y, \qquad \frac{dy}{dt} = -5x + 4y$$

$$A = \begin{bmatrix} -6 & 5 \\ -5 & 4 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (-6 - \lambda)(4 - \lambda) + 25 = \lambda^2 + 2\lambda + 1 = (\lambda + 1)^2 = 0$$

$$\boxed{\lambda_{1,2} = -1 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = -1$:

$$A + I = \begin{bmatrix} -5 & 5 \\ -5 & 5 \end{bmatrix} \implies v_1 = v_2$$

$$\boxed{k_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}}$$

**Autovetor generalizado** via $(A + I)p = k_1$:

$$\begin{bmatrix} -5 & 5 \\ -5 & 5 \end{bmatrix} \begin{pmatrix} p_1 \\ p_2 \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

Da primeira linha: $-5p_1 + 5p_2 = 1$. Escolhendo $p_1 = 0 \Rightarrow p_2 = \tfrac{1}{5}$:

$$\boxed{p = \begin{pmatrix} 0 \\ \tfrac{1}{5} \end{pmatrix}}$$

### Solução Geral

$$\boxed{X(t) = c_1 \begin{pmatrix} 1 \\ 1 \end{pmatrix} e^{-t} + c_2 \left[ \begin{pmatrix} 1 \\ 1 \end{pmatrix} t + \begin{pmatrix} 0 \\ \frac{1}{5} \end{pmatrix} \right] e^{-t}}$$

### Estabilidade

$\mathrm{Re}(\lambda) = -1 < 0$ para ambos.

> **Assintoticamente estável** — nó atrator degenerado (estrela imprópria).

---

## (c)

$$\dot{x} = \begin{bmatrix} -1 & 3 \\ -3 & 5 \end{bmatrix} x$$

$$A = \begin{bmatrix} -1 & 3 \\ -3 & 5 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (-1 - \lambda)(5 - \lambda) + 9 = \lambda^2 - 4\lambda + 4 = (\lambda - 2)^2 = 0$$

$$\boxed{\lambda_{1,2} = 2 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = 2$:

$$A - 2I = \begin{bmatrix} -3 & 3 \\ -3 & 3 \end{bmatrix} \implies v_1 = v_2$$

$$\boxed{k_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}}$$

**Autovetor generalizado** via $(A - 2I)p = k_1$:

$$\begin{bmatrix} -3 & 3 \\ -3 & 3 \end{bmatrix} \begin{pmatrix} p_1 \\ p_2 \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$

Da primeira linha: $-3p_1 + 3p_2 = 1$. Escolhendo $p_1 = 0 \Rightarrow p_2 = \tfrac{1}{3}$:

$$\boxed{p = \begin{pmatrix} 0 \\ \tfrac{1}{3} \end{pmatrix}}$$

### Solução Geral

$$\boxed{X(t) = c_1 \begin{pmatrix} 1 \\ 1 \end{pmatrix} e^{2t} + c_2 \left[ \begin{pmatrix} 1 \\ 1 \end{pmatrix} t + \begin{pmatrix} 0 \\ \frac{1}{3} \end{pmatrix} \right] e^{2t}}$$

### Estabilidade

$\mathrm{Re}(\lambda) = 2 > 0$ para ambos.

> **Instável** — nó repulsor degenerado, trajetórias divergem exponencialmente.

---

## (d)

$$\dot{x} = \begin{bmatrix} 12 & -9 \\ 4 & 0 \end{bmatrix} x$$

$$A = \begin{bmatrix} 12 & -9 \\ 4 & 0 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (12 - \lambda)(0 - \lambda) + 36 = \lambda^2 - 12\lambda + 36 = (\lambda - 6)^2 = 0$$

$$\boxed{\lambda_{1,2} = 6 \text{ (repetido)}}$$

### Autovetores

Para $\lambda = 6$:

$$A - 6I = \begin{bmatrix} 6 & -9 \\ 4 & -6 \end{bmatrix} \implies 6v_1 = 9v_2 \implies v_1 = \tfrac{3}{2}v_2$$

Escolhendo $v_2 = 2$:

$$\boxed{k_1 = \begin{pmatrix} 3 \\ 2 \end{pmatrix}}$$

**Autovetor generalizado** via $(A - 6I)p = k_1$:

$$\begin{bmatrix} 6 & -9 \\ 4 & -6 \end{bmatrix} \begin{pmatrix} p_1 \\ p_2 \end{pmatrix} = \begin{pmatrix} 3 \\ 2 \end{pmatrix}$$

Da segunda linha: $4p_1 - 6p_2 = 2 \Rightarrow 2p_1 - 3p_2 = 1$. Escolhendo $p_2 = 0 \Rightarrow p_1 = \tfrac{1}{2}$:

$$\boxed{p = \begin{pmatrix} \tfrac{1}{2} \\ 0 \end{pmatrix}}$$

### Solução Geral

$$\boxed{X(t) = c_1 \begin{pmatrix} 3 \\ 2 \end{pmatrix} e^{6t} + c_2 \left[ \begin{pmatrix} 3 \\ 2 \end{pmatrix} t + \begin{pmatrix} \frac{1}{2} \\ 0 \end{pmatrix} \right] e^{6t}}$$

### Estabilidade

$\mathrm{Re}(\lambda) = 6 > 0$ para ambos.

> **Instável** — nó repulsor degenerado, trajetórias divergem exponencialmente.

---

## Resumo

| Exercício | Autovalores | Tipo | Estabilidade |
|:---------:|:-----------:|:----:|:------------:|
| (a) | $\lambda = 0$ (repet.) | Nó degenerado (crescimento linear) | **Instável** |
| (b) | $\lambda = -1$ (repet.) | Nó atrator degenerado | **Assintoticamente estável** |
| (c) | $\lambda = 2$ (repet.) | Nó repulsor degenerado | **Instável** |
| (d) | $\lambda = 6$ (repet.) | Nó repulsor degenerado | **Instável** |
