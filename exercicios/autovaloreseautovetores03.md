# Autovalores Complexos, Autovetores e Estabilidade

Para sistemas $\dot{X} = AX$ com autovalores complexos $\lambda = \alpha \pm \beta j$, a estabilidade depende exclusivamente de $\alpha = \mathrm{Re}(\lambda)$:

| Condição | Classificação | Comportamento |
|---|---|---|
| $\alpha < 0$ | Assintoticamente estável | Espiral convergente |
| $\alpha = 0$ | Marginalmente estável | Centro (órbitas fechadas) |
| $\alpha > 0$ | Instável | Espiral divergente |

Para autovalores $\lambda = \alpha + \beta j$ com autovetor $k = B_1 + j B_2$, a solução geral real é:

$$X(t) = c_1 e^{\alpha t}[B_1 \cos(\beta t) - B_2 \sin(\beta t)] + c_2 e^{\alpha t}[B_1 \sin(\beta t) + B_2 \cos(\beta t)]$$

---

## (a)

$$\frac{dx}{dt} = 6x - y, \qquad \frac{dy}{dt} = 5x + 2y$$

$$A = \begin{bmatrix} 6 & -1 \\ 5 & 2 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (6-\lambda)(2-\lambda) + 5 = \lambda^2 - 8\lambda + 17 = 0$$

$$\lambda = \frac{8 \pm \sqrt{64 - 68}}{2} = \frac{8 \pm 2j}{2}$$

$$\boxed{\lambda_{1,2} = 4 \pm j}$$

### Autovetores

Para $\lambda_1 = 4 + j$, resolvemos $(A - (4+j)I)v = 0$:

$$\begin{bmatrix} 2-j & -1 \\ 5 & -2-j \end{bmatrix} v = 0$$

Da primeira linha: $(2-j)v_1 = v_2$. Escolhendo $v_1 = 1$:

$$k = \begin{pmatrix} 1 \\ 2-j \end{pmatrix} = \underbrace{\begin{pmatrix} 1 \\ 2 \end{pmatrix}}_{B_1} + j\underbrace{\begin{pmatrix} 0 \\ -1 \end{pmatrix}}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1 e^{4t}\left[\begin{pmatrix}1\\2\end{pmatrix}\cos t - \begin{pmatrix}0\\-1\end{pmatrix}\sin t\right] + c_2 e^{4t}\left[\begin{pmatrix}1\\2\end{pmatrix}\sin t + \begin{pmatrix}0\\-1\end{pmatrix}\cos t\right]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 4 > 0$.

> **Instável** — espiral divergente.

---

## (b)

$$\frac{dx}{dt} = x + y, \qquad \frac{dy}{dt} = -2x - y$$

$$A = \begin{bmatrix} 1 & 1 \\ -2 & -1 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (1-\lambda)(-1-\lambda) + 2 = \lambda^2 + 1 = 0$$

$$\boxed{\lambda_{1,2} = \pm j}$$

### Autovetores

Para $\lambda_1 = j$, resolvemos $(A - jI)v = 0$:

$$\begin{bmatrix} 1-j & 1 \\ -2 & -1-j \end{bmatrix} v = 0$$

Da primeira linha: $v_2 = -(1-j)v_1$. Escolhendo $v_1 = 1$:

$$k = \begin{pmatrix} 1 \\ -1+j \end{pmatrix} = \underbrace{\begin{pmatrix} 1 \\ -1 \end{pmatrix}}_{B_1} + j\underbrace{\begin{pmatrix} 0 \\ 1 \end{pmatrix}}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1 \left[\begin{pmatrix}1\\-1\end{pmatrix}\cos t - \begin{pmatrix}0\\1\end{pmatrix}\sin t\right] + c_2 \left[\begin{pmatrix}1\\-1\end{pmatrix}\sin t + \begin{pmatrix}0\\1\end{pmatrix}\cos t\right]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 0$.

> **Marginalmente estável** — centro, órbitas fechadas com frequência $\omega = 1\ \mathrm{rad/s}$.

---

## (c)

$$\frac{dx}{dt} = 5x + y, \qquad \frac{dy}{dt} = -2x + 3y$$

$$A = \begin{bmatrix} 5 & 1 \\ -2 & 3 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (5-\lambda)(3-\lambda) + 2 = \lambda^2 - 8\lambda + 17 = 0$$

$$\lambda = \frac{8 \pm \sqrt{64 - 68}}{2}$$

$$\boxed{\lambda_{1,2} = 4 \pm j}$$

### Autovetores

Para $\lambda_1 = 4 + j$:

$$\begin{bmatrix} 1-j & 1 \\ -2 & -1-j \end{bmatrix} v = 0$$

Da primeira linha: $v_2 = -(1-j)v_1$. Escolhendo $v_1 = 1$:

$$k = \begin{pmatrix} 1 \\ -1+j \end{pmatrix} = \underbrace{\begin{pmatrix} 1 \\ -1 \end{pmatrix}}_{B_1} + j\underbrace{\begin{pmatrix} 0 \\ 1 \end{pmatrix}}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1 e^{4t}\left[\begin{pmatrix}1\\-1\end{pmatrix}\cos t - \begin{pmatrix}0\\1\end{pmatrix}\sin t\right] + c_2 e^{4t}\left[\begin{pmatrix}1\\-1\end{pmatrix}\sin t + \begin{pmatrix}0\\1\end{pmatrix}\cos t\right]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 4 > 0$.

> **Instável** — espiral divergente.

---

## (d)

$$\frac{dx}{dt} = 4x + 5y, \qquad \frac{dy}{dt} = -2x + 6y$$

$$A = \begin{bmatrix} 4 & 5 \\ -2 & 6 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (4-\lambda)(6-\lambda) + 10 = \lambda^2 - 10\lambda + 34 = 0$$

$$\lambda = \frac{10 \pm \sqrt{100 - 136}}{2} = \frac{10 \pm 6j}{2}$$

$$\boxed{\lambda_{1,2} = 5 \pm 3j}$$

### Autovetores

Para $\lambda_1 = 5 + 3j$:

$$\begin{bmatrix} -1-3j & 5 \\ -2 & 1-3j \end{bmatrix} v = 0$$

Da primeira linha: $(-1-3j)v_1 = -5v_2$, ou seja $v_2 = \tfrac{1+3j}{5}v_1$. Escolhendo $v_1 = 5$:

$$k = \begin{pmatrix} 5 \\ 1+3j \end{pmatrix} = \underbrace{\begin{pmatrix} 5 \\ 1 \end{pmatrix}}_{B_1} + j\underbrace{\begin{pmatrix} 0 \\ 3 \end{pmatrix}}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1 e^{5t}\left[\begin{pmatrix}5\\1\end{pmatrix}\cos 3t - \begin{pmatrix}0\\3\end{pmatrix}\sin 3t\right] + c_2 e^{5t}\left[\begin{pmatrix}5\\1\end{pmatrix}\sin 3t + \begin{pmatrix}0\\3\end{pmatrix}\cos 3t\right]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 5 > 0$.

> **Instável** — espiral divergente.

---

## (e)

$$\dot{x} = \begin{bmatrix} 4 & -5 \\ 5 & -4 \end{bmatrix} x$$

$$A = \begin{bmatrix} 4 & -5 \\ 5 & -4 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (4-\lambda)(-4-\lambda) + 25 = \lambda^2 + 9 = 0$$

$$\boxed{\lambda_{1,2} = \pm 3j}$$

### Autovetores

Para $\lambda_1 = 3j$:

$$\begin{bmatrix} 4-3j & -5 \\ 5 & -4-3j \end{bmatrix} v = 0$$

Da primeira linha: $(4-3j)v_1 = 5v_2$. Escolhendo $v_1 = 5$:

$$k = \begin{pmatrix} 5 \\ 4-3j \end{pmatrix} = \underbrace{\begin{pmatrix} 5 \\ 4 \end{pmatrix}}_{B_1} + j\underbrace{\begin{pmatrix} 0 \\ -3 \end{pmatrix}}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1 \left[\begin{pmatrix}5\\4\end{pmatrix}\cos 3t - \begin{pmatrix}0\\-3\end{pmatrix}\sin 3t\right] + c_2 \left[\begin{pmatrix}5\\4\end{pmatrix}\sin 3t + \begin{pmatrix}0\\-3\end{pmatrix}\cos 3t\right]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 0$.

> **Marginalmente estável** — centro, órbitas fechadas com frequência $\omega = 3\ \mathrm{rad/s}$.

---

## (f)

$$\dot{x} = \begin{bmatrix} 1 & -8 \\ 1 & -3 \end{bmatrix} x$$

$$A = \begin{bmatrix} 1 & -8 \\ 1 & -3 \end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = (1-\lambda)(-3-\lambda) + 8 = \lambda^2 + 2\lambda + 5 = 0$$

$$\lambda = \frac{-2 \pm \sqrt{4 - 20}}{2} = \frac{-2 \pm 4j}{2}$$

$$\boxed{\lambda_{1,2} = -1 \pm 2j}$$

### Autovetores

Para $\lambda_1 = -1 + 2j$:

$$\begin{bmatrix} 2-2j & -8 \\ 1 & -2-2j \end{bmatrix} v = 0$$

Da segunda linha: $v_1 = (2+2j)v_2$. Escolhendo $v_2 = 1$:

$$k = \begin{pmatrix} 2+2j \\ 1 \end{pmatrix} = \underbrace{\begin{pmatrix} 2 \\ 1 \end{pmatrix}}_{B_1} + j\underbrace{\begin{pmatrix} 2 \\ 0 \end{pmatrix}}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1 e^{-t}\left[\begin{pmatrix}2\\1\end{pmatrix}\cos 2t - \begin{pmatrix}2\\0\end{pmatrix}\sin 2t\right] + c_2 e^{-t}\left[\begin{pmatrix}2\\1\end{pmatrix}\sin 2t + \begin{pmatrix}2\\0\end{pmatrix}\cos 2t\right]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = -1 < 0$.

> **Assintoticamente estável** — espiral convergente com frequência $\omega = 2\ \mathrm{rad/s}$.

---

## Resumo

| Exercício | Autovalores $\lambda$ | $\alpha = \mathrm{Re}(\lambda)$ | $\omega = \mathrm{Im}(\lambda)$ | Estabilidade |
|:---------:|:---------------------:|:-------------------------------:|:-------------------------------:|:------------:|
| (a) | $4 \pm j$ | $+4$ | $1$ | **Instável** (espiral divergente) |
| (b) | $\pm j$ | $0$ | $1$ | **Marginalmente estável** (centro) |
| (c) | $4 \pm j$ | $+4$ | $1$ | **Instável** (espiral divergente) |
| (d) | $5 \pm 3j$ | $+5$ | $3$ | **Instável** (espiral divergente) |
| (e) | $\pm 3j$ | $0$ | $3$ | **Marginalmente estável** (centro) |
| (f) | $-1 \pm 2j$ | $-1$ | $2$ | **Assintoticamente estável** (espiral convergente) |
