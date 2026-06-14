# Cálculo de $e^{At}$ — 8 matrizes

## Método geral

Para uma matriz $2\times2$, usamos a **fórmula de Sylvester** (via autovalores):

- **Autovalores distintos** $\lambda_1 \neq \lambda_2$:

$$e^{At} = \frac{e^{\lambda_1 t}(A - \lambda_2 I) - e^{\lambda_2 t}(A - \lambda_1 I)}{\lambda_1 - \lambda_2}$$

- **Autovalor repetido** $\lambda_1 = \lambda_2 = \lambda$:

$$e^{At} = e^{\lambda t}\left(I + (A - \lambda I)\,t\right)$$

- **Matriz diagonal** $A = \mathrm{diag}(\lambda_1, \lambda_2)$:

$$e^{At} = \mathrm{diag}(e^{\lambda_1 t},\; e^{\lambda_2 t})$$

---

## (a) — $A = [2,0;\;0,-3]$

Matriz **diagonal**. Autovalores: $\lambda_1 = 2$, $\lambda_2 = -3$.

$$\boxed{e^{At} = \begin{bmatrix} e^{2t} & 0 \\ 0 & e^{-3t} \end{bmatrix}}$$

---

## (b) — $A = [3,2;\;4,1]$

**Autovalores:** $\det(A-\lambda I) = (3-\lambda)(1-\lambda)-8 = \lambda^2-4\lambda-5 = (\lambda-5)(\lambda+1) = 0$

$$\lambda_1 = 5, \quad \lambda_2 = -1$$

**Aplicando Sylvester** com $\lambda_1 - \lambda_2 = 6$:

$$e^{At} = \frac{e^{5t}(A+I) - e^{-t}(A-5I)}{6}$$

$$A + I = [4,2;\;4,2], \qquad A - 5I = [-2,2;\;4,-4]$$

$$e^{At} = \frac{1}{6}\left(e^{5t}\begin{bmatrix}4&2\\4&2\end{bmatrix} - e^{-t}\begin{bmatrix}-2&2\\4&-4\end{bmatrix}\right)$$

$$\boxed{e^{At} = \begin{bmatrix} \dfrac{4e^{5t}+2e^{-t}}{6} & \dfrac{2e^{5t}-2e^{-t}}{6} \\[10pt] \dfrac{4e^{5t}-4e^{-t}}{6} & \dfrac{2e^{5t}+4e^{-t}}{6} \end{bmatrix} = \begin{bmatrix} \dfrac{2e^{5t}+e^{-t}}{3} & \dfrac{e^{5t}-e^{-t}}{3} \\[10pt] \dfrac{2(e^{5t}-e^{-t})}{3} & \dfrac{e^{5t}+2e^{-t}}{3} \end{bmatrix}}$$

---

## (c) — $A = [5,6;\;-4,-5]$

**Autovalores:** $\det(A-\lambda I) = (5-\lambda)(-5-\lambda)+24 = \lambda^2 - 1 = 0$

$$\lambda_1 = 1, \quad \lambda_2 = -1$$

**Aplicando Sylvester** com $\lambda_1 - \lambda_2 = 2$:

$$e^{At} = \frac{e^{t}(A+I) - e^{-t}(A-I)}{2}$$

$$A + I = [6,6;\;-4,-4], \qquad A - I = [4,6;\;-4,-6]$$

$$e^{At} = \frac{1}{2}\left(e^{t}\begin{bmatrix}6&6\\-4&-4\end{bmatrix} - e^{-t}\begin{bmatrix}4&6\\-4&-6\end{bmatrix}\right)$$

$$\boxed{e^{At} = \begin{bmatrix} 3e^{t}-2e^{-t} & 3e^{t}-3e^{-t} \\[6pt] -2e^{t}+2e^{-t} & -2e^{t}+3e^{-t} \end{bmatrix}}$$

**Verificação** em $t=0$: $[3-2,\ 3-3;\ -2+2,\ -2+3] = [1,0;0,1] = I$ ✓

---

## (d) — $A = [0,1;\;8,-2]$

**Autovalores:** $\det(A-\lambda I) = \lambda(\lambda+2)-8 = \lambda^2+2\lambda-8 = (\lambda-2)(\lambda+4) = 0$

$$\lambda_1 = 2, \quad \lambda_2 = -4$$

**Aplicando Sylvester** com $\lambda_1 - \lambda_2 = 6$:

$$e^{At} = \frac{e^{2t}(A+4I) - e^{-4t}(A-2I)}{6}$$

$$A + 4I = [4,1;\;8,2], \qquad A - 2I = [-2,1;\;8,-4]$$

$$e^{At} = \frac{1}{6}\left(e^{2t}\begin{bmatrix}4&1\\8&2\end{bmatrix} - e^{-4t}\begin{bmatrix}-2&1\\8&-4\end{bmatrix}\right)$$

$$\boxed{e^{At} = \begin{bmatrix} \dfrac{4e^{2t}+2e^{-4t}}{6} & \dfrac{e^{2t}-e^{-4t}}{6} \\[10pt] \dfrac{8e^{2t}-8e^{-4t}}{6} & \dfrac{2e^{2t}+4e^{-4t}}{6} \end{bmatrix} = \begin{bmatrix} \dfrac{2e^{2t}+e^{-4t}}{3} & \dfrac{e^{2t}-e^{-4t}}{6} \\[10pt] \dfrac{4(e^{2t}-e^{-4t})}{3} & \dfrac{e^{2t}+2e^{-4t}}{3} \end{bmatrix}}$$

---

## (e) — $A = [0,1;\;-14,-9]$

**Autovalores:** $\det(A-\lambda I) = \lambda(\lambda+9)+14 = \lambda^2+9\lambda+14 = (\lambda+2)(\lambda+7) = 0$

$$\lambda_1 = -2, \quad \lambda_2 = -7$$

**Aplicando Sylvester** com $\lambda_1 - \lambda_2 = 5$:

$$e^{At} = \frac{e^{-2t}(A+7I) - e^{-7t}(A+2I)}{5}$$

$$A + 7I = [7,1;\;-14,-2], \qquad A + 2I = [2,1;\;-14,-7]$$

$$e^{At} = \frac{1}{5}\left(e^{-2t}\begin{bmatrix}7&1\\-14&-2\end{bmatrix} - e^{-7t}\begin{bmatrix}2&1\\-14&-7\end{bmatrix}\right)$$

$$\boxed{e^{At} = \begin{bmatrix} \dfrac{7e^{-2t}-2e^{-7t}}{5} & \dfrac{e^{-2t}-e^{-7t}}{5} \\[10pt] \dfrac{-14e^{-2t}+14e^{-7t}}{5} & \dfrac{-2e^{-2t}+7e^{-7t}}{5} \end{bmatrix}}$$

**Verificação** em $t=0$: diagonal $= \frac{7-2}{5} = 1$, $\frac{-2+7}{5} = 1$; fora da diagonal $= \frac{1-1}{5}=0$, $\frac{-14+14}{5}=0$ → $I$ ✓

---

## (f) — $A = [2,0;\;0,2] = 2I$

Caso especial: $A = \lambda I$ com $\lambda = 2$. Como $A - \lambda I = 0$:

$$e^{At} = e^{2t} \cdot I$$

$$\boxed{e^{At} = \begin{bmatrix} e^{2t} & 0 \\ 0 & e^{2t} \end{bmatrix}}$$

---

## (g) — $A = [2,1;\;0,2]$

**Autovalor repetido:** $\lambda_{1,2} = 2$, com $A - 2I = [0,1;\;0,0]$ (bloco de Jordan).

Usando a fórmula para autovalor repetido:

$$e^{At} = e^{2t}\left(I + (A-2I)\,t\right) = e^{2t}\left(\begin{bmatrix}1&0\\0&1\end{bmatrix} + \begin{bmatrix}0&1\\0&0\end{bmatrix}t\right)$$

$$\boxed{e^{At} = e^{2t}\begin{bmatrix} 1 & t \\ 0 & 1 \end{bmatrix}}$$

Note que $(A-2I)^2 = [0,1;0,0]^2 = 0$ (matriz nilpotente), então a série de Taylor trunca naturalmente no primeiro termo — não há termos de ordem superior.

---

## (h) — $A = [4,-5;\;5,-4]$

**Autovalores:** $\det(A-\lambda I) = (4-\lambda)(-4-\lambda)+25 = \lambda^2+9 = 0$

$$\lambda_{1,2} = \pm 3j \quad (\alpha = 0,\; \beta = 3)$$

Para autovalores puramente imaginários, usamos a forma de Euler. Com $\lambda_1 - \lambda_2 = 6j$:

$$e^{At} = \frac{e^{3jt}(A-(-3j)I) - e^{-3jt}(A-3jI)}{6j}$$

Reagrupando em termos de $\cos(3t)$ e $\sin(3t)$, via $e^{\pm 3jt} = \cos 3t \pm j\sin 3t$:

$$e^{At} = I\cos(3t) + \frac{A}{\beta}\sin(3t) \quad \text{(pois } \alpha = 0\text{)}$$

$$\frac{A}{3} = \begin{bmatrix}4/3 & -5/3\\5/3 & -4/3\end{bmatrix}$$

$$\boxed{e^{At} = \begin{bmatrix} \cos 3t + \dfrac{4}{3}\sin 3t & -\dfrac{5}{3}\sin 3t \\[10pt] \dfrac{5}{3}\sin 3t & \cos 3t - \dfrac{4}{3}\sin 3t \end{bmatrix}}$$

**Verificação** em $t=0$: $[\cos 0, 0;\ 0, \cos 0] = I$ ✓

---

## Resumo

| | $A$ | Autovalores | Tipo | $e^{At}$ |
|:---:|:---:|:---:|:---:|:---:|
| (a) | $[2,0;\;0,-3]$ | $2,\,-3$ | Diagonal | $\mathrm{diag}(e^{2t}, e^{-3t})$ |
| (b) | $[3,2;\;4,1]$ | $5,\,-1$ | Reais distintos | Sylvester |
| (c) | $[5,6;\;-4,-5]$ | $1,\,-1$ | Reais distintos | Sylvester |
| (d) | $[0,1;\;8,-2]$ | $2,\,-4$ | Reais distintos | Sylvester |
| (e) | $[0,1;\;-14,-9]$ | $-2,\,-7$ | Reais distintos | Sylvester |
| (f) | $2I$ | $2,\,2$ | Escalar | $e^{2t}I$ |
| (g) | $[2,1;\;0,2]$ | $2,\,2$ | Jordan | $e^{2t}(I + Nt)$ |
| (h) | $[4,-5;\;5,-4]$ | $\pm 3j$ | Imaginários puros | $I\cos\beta t + \frac{A}{\beta}\sin\beta t$ |
