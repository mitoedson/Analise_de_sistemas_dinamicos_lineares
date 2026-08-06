# Autovalores Complexos, Autovetores e Estabilidade

Para sistemas $\dot{X} = AX$ com autovalores complexos $\lambda = \alpha \pm \beta j$, a estabilidade depende exclusivamente de $\alpha = \mathrm{Re}(\lambda)$:

| Condição | Classificação | Comportamento |
|---|---|---|
| $\alpha < 0$ | Assintoticamente estável | Espiral convergente |
| $\alpha = 0$ | Marginalmente estável | Centro (órbitas fechadas) |
| $\alpha > 0$ | Instável | Espiral divergente |

<ul>
<li>Foco Estável: Ocorre se a parte real for negativa (α<0). O sistema converge para a origem em forma de espiral
<li>Foco Instável: Ocorre se a parte real for positiva (α>0). O sistema se afasta da origem em espiral
<li>Centro: Ocorre se a parte real for nula (α=0). As trajetórias são ciclos fechados (elipses) em torno da origem, caracterizando estabilidade marginal (estável, mas não assintoticamente)
</ul>

Para autovalores $\lambda = \alpha + \beta j$ com autovetor $k = B_1 + j B_2$, a solução geral real é:

$$X(t) = c_1 e^{\alpha t}[B_1 \cos(\beta t) - B_2 \sin(\beta t)] + c_2 e^{\alpha t}[B_1 \sin(\beta t) + B_2 \cos(\beta t)]$$

---

(a)
<p>
$\frac{dx}{dt} = 6x - y, \qquad \frac{dy}{dt} = 5x + 2y$

$A = [6, -1; 5, 2]$

### Autovalores

$\det(A - \lambda I) = (6-\lambda)(2-\lambda) + 5 = \lambda^2 - 8\lambda + 17 = 0$

$\lambda = \frac{8 \pm \sqrt{64 - 68}}{2} = \frac{8 \pm 2j}{2}$

$\boxed{\lambda_{1,2} = 4 \pm j}$

### Autovetores

Para $\lambda_1 = 4 + j$, resolvemos $(A - (4+j)I)k = 0$:

$[2-j, -1; 5, -2-j] \cdot k = 0$

Da primeira linha: $(2-j)k_1 = k_2$. Escolhendo $k_1 = 1$:

$$k = (1; 2-j) = \underbrace{(1;2)}_{B_1} + j\underbrace{(0;-1)}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1\,e^{4t}\bigl[(1;2)\cos t - (0;-1)\sin t\bigr] + c_2\,e^{4t}\bigl[(1;2)\sin t + (0;-1)\cos t\bigr]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 4 > 0$.

> **Instável** — espiral divergente.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/6d3e8a26-1020-476f-8daa-ba505bc72ce7" />

<p><br>
<b>Retrato de fase:</b> espirais que se afastam da origem em sentido anti-horário (ou horário, dependendo da orientação do sistema). A cada volta, a distância à origem aumenta.
<p><b>Resposta temporal:</b> oscilações de amplitude crescente com frequência $\omega = 1\ \mathrm{rad/s}$, envelope dominado por $e^{4t}$. O crescimento é rápido — o intervalo plotado é curto ($t \in [0, 1.2]$).
<p><b>Classificação:</b> Instável — espiral divergente.

<hr>
<b>(b)</b>
<p>
$$\frac{dx}{dt} = x + y, \qquad \frac{dy}{dt} = -2x - y$$

$$A = [1, 1; -2, -1]$$

### Autovalores

$$\det(A - \lambda I) = (1-\lambda)(-1-\lambda) + 2 = \lambda^2 + 1 = 0$$

$$\boxed{\lambda_{1,2} = \pm j}$$

### Autovetores

Para $\lambda_1 = j$, resolvemos $(A - jI)\,v = 0$:

$$[1-j, 1; -2, -1-j] \cdot v = 0$$

Da primeira linha: $v_2 = -(1-j)v_1$. Escolhendo $v_1 = 1$:

$$k = (1; -1+j) = \underbrace{(1;-1)}_{B_1} + j\underbrace{(0;1)}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1\bigl[(1;-1)\cos t - (0;1)\sin t\bigr] + c_2\bigl[(1;-1)\sin t + (0;1)\cos t\bigr]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 0$.

> **Marginalmente estável** — centro, órbitas fechadas com frequência $\omega = 1\ \mathrm{rad/s}$.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/55707ff7-2def-48f9-908c-722a9af5855a" />
<p><br>
<b>Retrato de fase:</b> elipses fechadas centradas na origem — o sistema orbita sem jamais convergir ou divergir. Cada condição inicial define uma elipse própria (não há atração entre órbitas).
<p><b>Resposta temporal:</b> oscilações puramente periódicas, sem amortecimento, com frequência $\omega = 1\ \mathrm{rad/s}$. As amplitudes de $x_1(t)$ e $x_2(t)$ permanecem constantes para sempre.
<p>
<b>Classificação:</b> Marginalmente estável — centro.


<hr>
<b>(c)</b>
<p>
$$\frac{dx}{dt} = 5x + y, \qquad \frac{dy}{dt} = -2x + 3y$$

$$A = [5, 1; -2, 3]$$

### Autovalores

$$\det(A - \lambda I) = (5-\lambda)(3-\lambda) + 2 = \lambda^2 - 8\lambda + 17 = 0$$

$$\lambda = \frac{8 \pm \sqrt{64 - 68}}{2}$$

$$\boxed{\lambda_{1,2} = 4 \pm j}$$

### Autovetores

Para $\lambda_1 = 4 + j$:

$$[1-j, 1; -2, -1-j] \cdot v = 0$$

Da primeira linha: $v_2 = -(1-j)v_1$. Escolhendo $v_1 = 1$:

$$k = (1; -1+j) = \underbrace{(1;-1)}_{B_1} + j\underbrace{(0;1)}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1\,e^{4t}\bigl[(1;-1)\cos t - (0;1)\sin t\bigr] + c_2\,e^{4t}\bigl[(1;-1)\sin t + (0;1)\cos t\bigr]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 4 > 0$.

> **Instável** — espiral divergente.

<img width="600" alt="image" src="https://github.com/user-attachments/assets/2d8e139e-b9c9-430f-870b-8a7a6921d5a6" />

<p><br>
<b>Retrato de fase:</b> espirais divergentes, idênticas em tipo às do exercício (C-a), pois os autovalores são os mesmos ($4 \pm j$). A diferença está na orientação das espirais, determinada pelos autovetores de $A$.
<p><b>Resposta temporal:</b> oscilações crescentes com envelope $e^{4t}$ e frequência $\omega = 1\ \mathrm{rad/s}$.
<p>
<b>Classificação:</b> Instável — espiral divergente.
<p>
<b>Nota:</b> (C-a) e (C-c) têm os mesmos autovalores mas matrizes distintas. O comportamento qualitativo é idêntico; a diferença está na geometria precisa (inclinação e excentricidade) das espirais.


<hr>
<b>(d)</b>
<p>
$$\frac{dx}{dt} = 4x + 5y, \qquad \frac{dy}{dt} = -2x + 6y$$

$$A = [4, 5; -2, 6]$$

### Autovalores

$$\det(A - \lambda I) = (4-\lambda)(6-\lambda) + 10 = \lambda^2 - 10\lambda + 34 = 0$$

$$\lambda = \frac{10 \pm \sqrt{100 - 136}}{2} = \frac{10 \pm 6j}{2}$$

$$\boxed{\lambda_{1,2} = 5 \pm 3j}$$

### Autovetores

Para $\lambda_1 = 5 + 3j$:

$$[-1-3j, 5; -2, 1-3j] \cdot v = 0$$

Da primeira linha: $(-1-3j)v_1 = -5v_2 \Rightarrow v_2 = \tfrac{1+3j}{5}v_1$. Escolhendo $v_1 = 5$:

$$k = (5; 1+3j) = \underbrace{(5;1)}_{B_1} + j\underbrace{(0;3)}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1\,e^{5t}\bigl[(5;1)\cos 3t - (0;3)\sin 3t\bigr] + c_2\,e^{5t}\bigl[(5;1)\sin 3t + (0;3)\cos 3t\bigr]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 5 > 0$.

> **Instável** — espiral divergente.

<img width="600" alt="image" src="https://github.com/user-attachments/assets/b2975ac7-06d5-4a0c-b606-d95d513191ba" />

<p>
<b>Retrato de fase:</b> espirais divergentes com frequência angular maior ($\omega = 3\ \mathrm{rad/s}$) — as voltas são mais "apertadas" do que em (C-a/C-c). O crescimento é ainda mais rápido ($\alpha = 5$).
<p>
<b>Resposta temporal:</b> oscilações de alta frequência com amplitude dominada por $e^{5t}$. O intervalo plotado é muito curto ($t \in [0, 0.8]$) para manter legibilidade.
<p>
<b>Classificação:</b> Instável — espiral divergente.
<hr>
<b>(e)</b>
<p>
$\dot{x} = [4, -5; 5, -4]\,x$
<p>
$A = [4, -5; 5, -4]$

### Autovalores

$$\det(A - \lambda I) = (4-\lambda)(-4-\lambda) + 25 = \lambda^2 + 9 = 0$$

$$\boxed{\lambda_{1,2} = \pm 3j}$$

### Autovetores

Para $\lambda_1 = 3j$:

$$[4-3j, -5; 5, -4-3j] \cdot v = 0$$

Da primeira linha: $(4-3j)v_1 = 5v_2$. Escolhendo $v_1 = 5$:

$$k = (5; 4-3j) = \underbrace{(5;4)}_{B_1} + j\underbrace{(0;-3)}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1\bigl[(5;4)\cos 3t - (0;-3)\sin 3t\bigr] + c_2\bigl[(5;4)\sin 3t + (0;-3)\cos 3t\bigr]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = 0$.

> **Marginalmente estável** — centro, órbitas fechadas com frequência $\omega = 3\ \mathrm{rad/s}$.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/1af03be9-e792-4e39-8832-77889115f56b" />
<p>
- <b>Retrato de fase:</b> elipses fechadas com frequência $\omega = 3\ \mathrm{rad/s}$ — órbitas mais rápidas que as do exercício (C-b). As elipses têm inclinação e excentricidade determinadas pelos autovetores de $A$.
<p>
- <b>Resposta temporal:</b> oscilações puramente periódicas com frequência $\omega = 3\ \mathrm{rad/s}$ e amplitude constante.
<p>
**Classificação:** Marginalmente estável — centro.

<hr>
<b>(f)</b> 

$$\dot{x} = [1, -8; 1, -3]\,x$$
<p>
Obtemos $A = [1, -8; 1, -3]$

<b>Autovalores:</b>

$\det(A - \lambda I) = (1-\lambda)(-3-\lambda) + 8 = \lambda^2 + 2\lambda + 5 = 0$

$\lambda = \frac{-2 \pm \sqrt{4 - 20}}{2} = \frac{-2 \pm 4j}{2}$

$\boxed{\lambda_{1,2} = -1 \pm 2j}$

<p>
<b>Autovetores:</b>

Para $\lambda_1 = -1 + 2j$:

$$[2-2j, -8; 1, -2-2j] \cdot v = 0$$

Da segunda linha: $v_1 = (2+2j)v_2$. Escolhendo $v_2 = 1$:

$$k = (2+2j; 1) = \underbrace{(2;1)}_{B_1} + j\underbrace{(2;0)}_{B_2}$$

### Solução Geral

$$\boxed{X(t) = c_1\,e^{-t}\bigl[(2;1)\cos 2t - (2;0)\sin 2t\bigr] + c_2\,e^{-t}\bigl[(2;1)\sin 2t + (2;0)\cos 2t\bigr]}$$

### Estabilidade

$\alpha = \mathrm{Re}(\lambda) = -1 < 0$.

> **Assintoticamente estável** — espiral convergente com frequência $\omega = 2\ \mathrm{rad/s}$.

<img width="800" alt="image" src="https://github.com/user-attachments/assets/25194d0b-8e78-45b5-b1b3-6f51f5930fa9" />
<p>
<b>Retrato de fase:</b> espirais que convergem para a origem — o único caso assintoticamente estável do bloco complexo. As trajetórias giram enquanto se aproximam da origem, formando uma espiral interna.
<p>
<b>Resposta temporal:</b> oscilações de amplitude decrescente com frequência $\omega = 2\ \mathrm{rad/s}$, envelope dominado por $e^{-t}$. As curvas de $x_1(t)$ e $x_2(t)$ oscilam e decaem simultaneamente até zero.
<p>
</b>Classificação:</b> Assintoticamente estável — espiral convergente.

## Resumo

| Exercício | $A$ | Autovalores $\lambda$ | $\alpha$ | $\omega$ | Estabilidade |
|:---------:|:---:|:---------------------:|:--------:|:--------:|:------------:|
| (a) | $[6,-1;5,2]$ | $4 \pm j$ | $+4$ | $1$ | **Instável** (espiral divergente) |
| (b) | $[1,1;-2,-1]$ | $\pm j$ | $0$ | $1$ | **Marginalmente estável** (centro) |
| (c) | $[5,1;-2,3]$ | $4 \pm j$ | $+4$ | $1$ | **Instável** (espiral divergente) |
| (d) | $[4,5;-2,6]$ | $5 \pm 3j$ | $+5$ | $3$ | **Instável** (espiral divergente) |
| (e) | $[4,-5;5,-4]$ | $\pm 3j$ | $0$ | $3$ | **Marginalmente estável** (centro) |
| (f) | $[1,-8;1,-3]$ | $-1 \pm 2j$ | $-1$ | $2$ | **Assintoticamente estável** (espiral convergente) |

---

[Ver teoria](teoria/autovaloreseautovetores.md)
