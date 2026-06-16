# Cálculo da Matriz Exponencial — Equações Diferenciais

## Método geral

Toda EDO de segunda ordem $\ddot{x} + a\dot{x} + bx = f(t)$ é convertida para espaço de estados com $x_1 = x$, $x_2 = \dot{x}$:
<p>
$$\begin{pmatrix}\dot{x}_1 \\ \dot{x}_2\end{pmatrix} = \underbrace{\begin{bmatrix}0 & 1\\ -b & -a\end{bmatrix}}_{A}\begin{pmatrix}x_1\\x_2\end{pmatrix} + \begin{pmatrix}0\\f(t)\end{pmatrix}$$

A solução é $X(t) = e^{At}X(t_0) + \int_{t_0}^{t} e^{A(t-\tau)}B\,f(\tau)\,d\tau$.

Para $f(t) = 0$ (homogênea): $X(t) = e^{At}X(t_0)$.

<hr>
<p>
<b>(a)</b> 
$$\ddot{x} + 2\dot{x} - 8x = 0,\ x(1)=1,\ \dot{x}(1)=0,\ f(t)=0$$

Espaço de estados
<p>
$$A = \begin{bmatrix}0 & 1\\ 8 & -2\end{bmatrix}$$

Autovalores
<p>
$$\det(A - \lambda I) = \lambda^2 + 2\lambda - 8 = (\lambda - 2)(\lambda + 4) = 0$$

$$\lambda_1 = 2, \quad \lambda_2 = -4$$

$e^{At}$ — Cayley-Hamilton
<p>
$$e^{\lambda_1 t} = e^{2t}:  \quad e^{2t} = \alpha_0 + 2\alpha_1$$

$$e^{\lambda_2 t} = e^{-4t}: \quad e^{-4t} = \alpha_0 - 4\alpha_1$$

Subtraindo: $e^{2t} - e^{-4t} = 6\alpha_1 \implies \alpha_1 = \dfrac{e^{2t} - e^{-4t}}{6}$

Somando convenientemente: $\alpha_0 = \dfrac{2e^{2t} + 4e^{-4t}}{6} + \dfrac{e^{-4t}-e^{-4t}}{6}$... da primeira: $\alpha_0 = e^{2t} - 2\alpha_1 = e^{2t} - \dfrac{e^{2t}-e^{-4t}}{3} = \dfrac{2e^{2t}+e^{-4t}}{3} - \dfrac{e^{-4t}}{3}$

Resolvendo o sistema diretamente:

$$\alpha_0 = \frac{4e^{2t} + 2e^{-4t}}{6} = \frac{2e^{2t}+e^{-4t}}{3}, \qquad \alpha_1 = \frac{e^{2t}-e^{-4t}}{6}$$

$$e^{At} = \alpha_0 I + \alpha_1 A = \frac{2e^{2t}+e^{-4t}}{3}\begin{bmatrix}1&0\\0&1\end{bmatrix} + \frac{e^{2t}-e^{-4t}}{6}\begin{bmatrix}0&1\\8&-2\end{bmatrix}$$

$$\boxed{e^{At} = \begin{bmatrix} \dfrac{2e^{2t}+e^{-4t}}{3} & \dfrac{e^{2t}-e^{-4t}}{6} \\[10pt] \dfrac{4(e^{2t}-e^{-4t})}{3} & \dfrac{e^{2t}+2e^{-4t}}{3} \end{bmatrix}}$$

Sistema homogêneo com $t_0 = 1$: $X(t) = e^{A(t-1)}X_0$, com $X_0 = (1;\,0)$.

$$x(t) = \frac{2e^{2(t-1)}+e^{-4(t-1)}}{3}, \qquad \dot{x}(t) = \frac{4(e^{2(t-1)}-e^{-4(t-1)})}{3}$$

$$\boxed{x(t) = \frac{2e^{2(t-1)}+e^{-4(t-1)}}{3}}$$

Claro! Vamos devagar passo a passo.

---

## Item (a) — $\ddot{x} + 2\dot{x} - 8x = 0$, $x(1) = 1$, $\dot{x}(1) = 0$

### Passo 1 — Espaço de estados

Definimos $x_1 = x$ e $x_2 = \dot{x}$, então:

$$\dot{x}_1 = x_2$$
$$\dot{x}_2 = \ddot{x} = 8x - 2\dot{x} = 8x_1 - 2x_2$$

Em forma matricial:

$$\underbrace{\begin{pmatrix}\dot{x}_1\\\dot{x}_2\end{pmatrix}}_{\dot{X}} = \underbrace{\begin{bmatrix}0&1\\8&-2\end{bmatrix}}_{A}\underbrace{\begin{pmatrix}x_1\\x_2\end{pmatrix}}_{X}$$

---

### Passo 2 — Condição inicial

Como $t_0 = 1$:

$$X(t_0) = X(1) = \begin{pmatrix}x(1)\\\dot{x}(1)\end{pmatrix} = \begin{pmatrix}1\\0\end{pmatrix}$$

---

### Passo 3 — Solução

Sistema homogêneo com $t_0 = 1$:

$$X(t) = e^{A(t-1)}X(1)$$

Substituindo $t \to t-1$ na matriz exponencial já calculada:

$$e^{A(t-1)} = \begin{bmatrix} \dfrac{2e^{2(t-1)}+e^{-4(t-1)}}{3} & \dfrac{e^{2(t-1)}-e^{-4(t-1)}}{6} \\[10pt] \dfrac{4(e^{2(t-1)}-e^{-4(t-1)})}{3} & \dfrac{e^{2(t-1)}+2e^{-4(t-1)}}{3} \end{bmatrix}$$

---

### Passo 4 — Multiplicar por $X(1) = (1;\,0)$

Apenas a **primeira coluna** de $e^{A(t-1)}$ contribui, pois $x_2(1) = 0$:

$$X(t) = \begin{bmatrix} \dfrac{2e^{2(t-1)}+e^{-4(t-1)}}{3} & \dfrac{e^{2(t-1)}-e^{-4(t-1)}}{6} \\[10pt] \dfrac{4(e^{2(t-1)}-e^{-4(t-1)})}{3} & \dfrac{e^{2(t-1)}+2e^{-4(t-1)}}{3} \end{bmatrix}\begin{pmatrix}1\\0\end{pmatrix}$$

$$= \begin{pmatrix} \dfrac{2e^{2(t-1)}+e^{-4(t-1)}}{3} \\[10pt] \dfrac{4(e^{2(t-1)}-e^{-4(t-1)})}{3} \end{pmatrix}$$

---

### Resultado

$$\boxed{x(t) = x_1(t) = \frac{2e^{2(t-1)}+e^{-4(t-1)}}{3}}$$

$$\dot{x}(t) = x_2(t) = \frac{4(e^{2(t-1)}-e^{-4(t-1)})}{3}$$

---

### Verificação em $t = 1$

$$x(1) = \frac{2e^0 + e^0}{3} = \frac{2+1}{3} = 1 \quad \checkmark$$

$$\dot{x}(1) = \frac{4(e^0 - e^0)}{3} = 0 \quad \checkmark$$


<hr>
<p>
<b>(a)</b> 
$$\ddot{x} + 2\dot{x} - 8x = 0,\ x(1)=1,\ \dot{x}(1)=0$$

Equação característica: $r^2+2r-8=0 \Rightarrow r = -4;2$.  
Solução geral: $x(t)=c_1 e^{-4t}+c_2 e^{2t}$.  
Condições iniciais em $t=1$:  
<p>
$c_1 e^{-4}+c_2 e^{2}=1$

$-4c_1 e^{-4}+2c_2 e^{2}=0$

$\Rightarrow c_1=\frac{e^{4}}{3}; c_2=\frac{2e^{-2}}{3}.$  
<p>
$\boxed{x(t)=\frac{1}{3}e^{4(1-t)}+\frac{2}{3}e^{2(t-1)}}$

<hr>
<p><b>(b)</b> 
$\ddot{x} + 2\dot{x} - 8x = 4, x(0)=0, \dot{x}(0)=0$

Solução homogênea: $x_h=c_1 e^{-4t}+c_2 e^{2t}$.  
Solução particular constante: $x_p = A \Rightarrow -8A=4 \Rightarrow A=-\frac12$.  
Geral: $x(t)=c_1 e^{-4t}+c_2 e^{2t}-\frac12$.  
Aplicando $x(0)=0; \dot{x}(0)=0$:  
<p>
$c_1+c_2-\frac12=0$
  
$-4c_1+2c_2=0$

$\Rightarrow c_1=\frac16\; c_2=\frac13.$
<p>$\boxed{x(t)=\frac16 e^{-4t}+\frac13 e^{2t}-\frac12}$

<hr>
<p><b>(c)</b> $\ddot{x} + 2\dot{x} - 8x = 4,\; x(1)=0,\; \dot{x}(1)=0$

Geral: $x(t)=c_1 e^{-4t}+c_2 e^{2t}-\frac12$.  
Condições em $t=1$:  
<p>
$c_1 e^{-4}+c_2 e^{2}=\frac12$
  
$-4c_1 e^{-4}+2c_2 e^{2}=0$

$\Rightarrow c_1=\frac{e^{4}}{6},\; c_2=\frac{e^{-2}}{3}.$  
<p>$\boxed{x(t)=\frac16 e^{4(1-t)}+\frac13 e^{2(t-1)}-\frac12}$

<hr>
<p><b>(d)</b> $\ddot{x} + 2\dot{x} - 8x = 4,\; x(0)=1,\; \dot{x}(0)=2$

Geral: $x(t)=c_1 e^{-4t}+c_2 e^{2t}-\frac12$.  
IC: $x(0)=c_1+c_2-\frac12=1 \Rightarrow c_1+c_2=\frac32$;  
$\dot{x}(0)=-4c_1+2c_2=2 \Rightarrow -2c_1+c_2=1$.  
Resolvendo: $c_1=\frac16,\; c_2=\frac43$.  
<p>
$\boxed{x(t)=\frac16 e^{-4t}+\frac43 e^{2t}-\frac12}$

<hr>
<p><b>(e)</b> $\ddot{x} + x = 0$

Equação característica: $r^2+1=0 \Rightarrow r=\pm i$.  
<p>$\boxed{x(t)=c_1\cos(t) + c_2\sin(t)}$

<hr>
<p><b>(f)</b> $\ddot{x} + x = 0,\; x(2)=0,\; \dot{x}(2)=0$

A única solução que satisfaz ambas as condições é a trivial.  
<p>
$\boxed{x(t)=0}$

<hr>
<p><b>(g)</b> $\ddot{x} + x = t,\; x(1)=0,\; \dot{x}(1)=1$

Solução particular: $x_p = t$ (pois $\ddot{t}=0$).  
Geral: $x(t)=c_1\cos t + c_2\sin t + t$.  
Aplicando as condições em $t=1$:  
<p>
$c_1\cos1 + c_2\sin1 + 1 = 0$
  
$-c_1\sin1 + c_2\cos1 + 1 = 1$

  
$\Rightarrow c_1\cos1 + c_2\sin1 = -1 \\ -c_1\sin1 + c_2\cos1 = 0$

Resolvendo: $c_1 = -\cos1,\; c_2 = -\sin1$.  

<p>$x(t)= -\cos1\cos t - \sin1\sin t + t = t - \cos(t-1).$  
<p>$\boxed{x(t)=t-\cos(t-1)}$

<hr>
<p><b>(h)</b> $\ddot{y} - \dot{y} - 2y = 0$

Equação característica: $r^2 - r -2=0 \Rightarrow r=2; -1$.  
<p>
$\boxed{y(t)=c_1 e^{2t}+c_2 e^{-t}}$

<hr>
<p><b>(i)</b>Sistema $\dot{x} = -4x+6y,\; \dot{y} = -3x+5y,\; x(0)=3,\; y(0)=2$

Matriz $A = \begin{bmatrix}-4 & 6 \\ -3 & 5\end{bmatrix}$.  
Autovalores: $\lambda_1=2,\; \lambda_2=-1\); autovetores: \((1,1)\) para \(\lambda=2\); \((2,1)\) para \(\lambda=-1$.  
Solução geral:  
$\begin{bmatrix}x\\y\end{bmatrix}=c_1 e^{2t}\begin{bmatrix}1\\1\end{bmatrix}+c_2 e^{-t}\begin{bmatrix}2\\1\end{bmatrix}.$  
IC: $c_1+2c_2=3,\; c_1+c_2=2 \Rightarrow c_1=1,\; c_2=1$.  
$\boxed{x(t)=e^{2t}+2e^{-t},\qquad y(t)=e^{2t}+e^{-t}}$

<hr>
<p><b>(j)</b>Sistema $\dot{x}+5x-12y=0,\; \dot{y}+2x-5y=0,\; x(0)=8,\; y(0)=3$

Reescrevendo: $\dot{x} = -5x+12y,\quad \dot{y} = -2x+5y$.  
Matriz $A = \begin{bmatrix}-5 & 12 \\ -2 & 5\end{bmatrix}$.  
Autovalores: $\lambda_1=1,\; \lambda_2=-1$; 
Autovetores: $((2,1)\) para \(\lambda=1\); \((3,1)\) para \(\lambda=-1$.  
<p>
Solução geral: 
<p>
$\begin{bmatrix}x\\y\end{bmatrix}=c_1 e^{t}\begin{bmatrix}2\\1\end{bmatrix}+c_2 e^{-t}\begin{bmatrix}3\\1\end{bmatrix}.$  
IC: $2c_1+3c_2=8,\quad c_1+c_2=3 \Rightarrow c_1=1,\; c_2=2$.  
<p>$\boxed{x(t)=2e^{t}+6e^{-t},\qquad y(t)=e^{t}+2e^{-t}}$



<hr>
# Cálculo da Matriz Exponencial — Equações Diferenciais

## Método geral

Toda EDO de segunda ordem $\ddot{x} + a\dot{x} + bx = f(t)$ é convertida para espaço de estados com $x_1 = x$, $x_2 = \dot{x}$:

$$\begin{pmatrix}\dot{x}_1\\\dot{x}_2\end{pmatrix} = \underbrace{\begin{bmatrix}0 & 1\\ -b & -a\end{bmatrix}}_{A}\begin{pmatrix}x_1\\x_2\end{pmatrix} + \begin{pmatrix}0\\f(t)\end{pmatrix}$$

A solução é $X(t) = e^{At}X(t_0) + \int_{t_0}^{t} e^{A(t-\tau)}B\,f(\tau)\,d\tau$.

Para $f(t) = 0$ (homogênea): $X(t) = e^{At}X(t_0)$.

---

## Itens (a) a (d) — $\ddot{x} + 2\dot{x} - 8x = f(t)$

### Espaço de estados

$$A = \begin{bmatrix}0 & 1\\ 8 & -2\end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = \lambda^2 + 2\lambda - 8 = (\lambda - 2)(\lambda + 4) = 0$$

$$\lambda_1 = 2, \quad \lambda_2 = -4$$

### $e^{At}$ — Cayley-Hamilton

$$e^{\lambda_1 t} = e^{2t}:  \quad e^{2t} = \alpha_0 + 2\alpha_1$$

$$e^{\lambda_2 t} = e^{-4t}: \quad e^{-4t} = \alpha_0 - 4\alpha_1$$

Subtraindo: $e^{2t} - e^{-4t} = 6\alpha_1 \implies \alpha_1 = \dfrac{e^{2t} - e^{-4t}}{6}$

Somando convenientemente: $\alpha_0 = \dfrac{2e^{2t} + 4e^{-4t}}{6} + \dfrac{e^{-4t}-e^{-4t}}{6}$... da primeira: $\alpha_0 = e^{2t} - 2\alpha_1 = e^{2t} - \dfrac{e^{2t}-e^{-4t}}{3} = \dfrac{2e^{2t}+e^{-4t}}{3} - \dfrac{e^{-4t}}{3}$

Resolvendo o sistema diretamente:

$$\alpha_0 = \frac{4e^{2t} + 2e^{-4t}}{6} = \frac{2e^{2t}+e^{-4t}}{3}, \qquad \alpha_1 = \frac{e^{2t}-e^{-4t}}{6}$$

$$e^{At} = \alpha_0 I + \alpha_1 A = \frac{2e^{2t}+e^{-4t}}{3}\begin{bmatrix}1&0\\0&1\end{bmatrix} + \frac{e^{2t}-e^{-4t}}{6}\begin{bmatrix}0&1\\8&-2\end{bmatrix}$$

$$\boxed{e^{At} = \begin{bmatrix} \dfrac{2e^{2t}+e^{-4t}}{3} & \dfrac{e^{2t}-e^{-4t}}{6} \\[10pt] \dfrac{4(e^{2t}-e^{-4t})}{3} & \dfrac{e^{2t}+2e^{-4t}}{3} \end{bmatrix}}$$

---

### (a) — $f(t)=0$, $x(1)=1$, $\dot{x}(1)=0$

Sistema homogêneo com $t_0 = 1$: $X(t) = e^{A(t-1)}X_0$, com $X_0 = (1;\,0)$.

$$x(t) = \frac{2e^{2(t-1)}+e^{-4(t-1)}}{3}, \qquad \dot{x}(t) = \frac{4(e^{2(t-1)}-e^{-4(t-1)})}{3}$$

$$\boxed{x(t) = \frac{2e^{2(t-1)}+e^{-4(t-1)}}{3}}$$

---

### (b) — $f(t)=4$, $x(0)=0$, $\dot{x}(0)=0$

Sistema não homogêneo com $t_0 = 0$, $X_0 = (0;\,0)$, $B = (0;\,1)$:

$$X(t) = \int_0^t e^{A(t-\tau)}\begin{pmatrix}0\\4\end{pmatrix}d\tau$$

Usando a segunda linha de $e^{A(t-\tau)}$ e integrando:

$$x(t) = 4\int_0^t \frac{e^{2(t-\tau)}-e^{-4(t-\tau)}}{6}\,d\tau = \frac{2}{3}\left[\frac{e^{2(t-\tau)}}{-2} + \frac{e^{-4(t-\tau)}}{-4}\right]_{\tau=0}^{t} \cdot (-1)$$

$$\boxed{x(t) = -\frac{1}{2} + \frac{e^{2t}}{3} + \frac{e^{-4t}}{6}}$$

---

### (c) — $f(t)=4$, $x(1)=0$, $\dot{x}(1)=0$

Mesmo que (b) mas com $t_0 = 1$:

$$\boxed{x(t) = -\frac{1}{2} + \frac{e^{2(t-1)}}{3} + \frac{e^{-4(t-1)}}{6}}$$

---

### (d) — $f(t)=4$, $x(0)=1$, $\dot{x}(0)=2$

Solução completa = homogênea + particular:

$$X(t) = e^{At}\begin{pmatrix}1\\2\end{pmatrix} + \int_0^t e^{A(t-\tau)}\begin{pmatrix}0\\4\end{pmatrix}d\tau$$

Parte homogênea (primeira linha de $e^{At}$ aplicada a $X_0 = (1;\,2)$):

$$x_h(t) = \frac{2e^{2t}+e^{-4t}}{3} + 2\cdot\frac{e^{2t}-e^{-4t}}{6} = \frac{2e^{2t}+e^{-4t}}{3} + \frac{e^{2t}-e^{-4t}}{3} = e^{2t}$$

Parte particular (de (b)): $x_p(t) = -\dfrac{1}{2} + \dfrac{e^{2t}}{3} + \dfrac{e^{-4t}}{6}$

$$\boxed{x(t) = -\frac{1}{2} + \frac{4e^{2t}}{3} + \frac{e^{-4t}}{6}}$$

---

## Itens (e), (f), (g) — $\ddot{x} + x = f(t)$

### Espaço de estados

$$A = \begin{bmatrix}0 & 1\\ -1 & 0\end{bmatrix}$$

### Autovalores

$$\det(A - \lambda I) = \lambda^2 + 1 = 0 \implies \lambda_{1,2} = \pm j \quad (\alpha=0,\;\beta=1)$$

### $e^{At}$ — Cayley-Hamilton

$$e^{jt} = \alpha_0 + j\alpha_1, \qquad e^{-jt} = \alpha_0 - j\alpha_1$$

Somando: $\alpha_0 = \cos t$. Subtraindo: $\alpha_1 = \sin t$.

$$e^{At} = \cos t\, I + \sin t\, A = \cos t\begin{bmatrix}1&0\\0&1\end{bmatrix} + \sin t\begin{bmatrix}0&1\\-1&0\end{bmatrix}$$

$$\boxed{e^{At} = \begin{bmatrix}\cos t & \sin t\\ -\sin t & \cos t\end{bmatrix}}$$

---

### (e) — $f(t)=0$, sem condições iniciais

Solução geral homogênea:

$$\boxed{x(t) = c_1\cos t + c_2\sin t}$$

---

### (f) — $f(t)=0$, $x(2)=0$, $\dot{x}(2)=0$

$X_0 = (0;\,0)$, portanto:

$$X(t) = e^{A(t-2)}\begin{pmatrix}0\\0\end{pmatrix} = \begin{pmatrix}0\\0\end{pmatrix}$$

$$\boxed{x(t) = 0}$$

---

### (g) — $f(t)=t$, $x(1)=0$, $\dot{x}(1)=1$, $t_0=1$

Parte homogênea com $X_0 = (0;\,1)$:

$$x_h(t) = \sin(t-1)$$

Parte particular via variação de parâmetros:

$$x_p(t) = \int_1^t \sin(t-\tau)\cdot\tau\,d\tau$$

Integrando por partes:

$$x_p(t) = \left[-\tau\cos(t-\tau)\right]_1^t + \int_1^t \cos(t-\tau)\,d\tau = -t + \cos(t-1) + \left[\sin(t-\tau)\right]_1^t$$

$$x_p(t) = -t + \cos(t-1) + \sin(t-1) \cdot 0 - \sin(0) = -t + \cos(t-1)$$

$$\boxed{x(t) = -t + \cos(t-1) + \sin(t-1)}$$

---

## Item (h) — $\ddot{y} - \dot{y} - 2y = 0$

### Espaço de estados

$$A = \begin{bmatrix}0 & 1\\ 2 & 1\end{bmatrix}$$

### Autovalores

$$\lambda^2 - \lambda - 2 = (\lambda-2)(\lambda+1) = 0 \implies \lambda_1 = 2,\;\lambda_2 = -1$$

### $e^{At}$ — Cayley-Hamilton

$$e^{2t} = \alpha_0 + 2\alpha_1, \qquad e^{-t} = \alpha_0 - \alpha_1$$

Subtraindo: $\alpha_1 = \dfrac{e^{2t}-e^{-t}}{3}$, \quad $\alpha_0 = \dfrac{e^{2t}+2e^{-t}}{3}$

$$e^{At} = \begin{bmatrix} \dfrac{e^{2t}+2e^{-t}}{3} & \dfrac{e^{2t}-e^{-t}}{3} \\[10pt] \dfrac{2(e^{2t}-e^{-t})}{3} & \dfrac{2e^{2t}+e^{-t}}{3} \end{bmatrix}$$

Solução geral (sem condições iniciais especificadas):

$$\boxed{y(t) = c_1 e^{2t} + c_2 e^{-t}}$$

---

## Item (i) — Sistema $2\times2$

$$\dot{x} = -4x + 6y, \qquad \dot{y} = -3x + 5y, \qquad x(0)=3,\;y(0)=2$$

$$A = \begin{bmatrix}-4 & 6\\ -3 & 5\end{bmatrix}$$

### Autovalores

$$\det(A-\lambda I) = (-4-\lambda)(5-\lambda)+18 = \lambda^2-\lambda-2 = (\lambda-2)(\lambda+1) = 0$$

$$\lambda_1 = 2, \quad \lambda_2 = -1$$

### $e^{At}$ — Cayley-Hamilton

$$\alpha_1 = \frac{e^{2t}-e^{-t}}{3}, \qquad \alpha_0 = \frac{e^{2t}+2e^{-t}}{3}$$

$$e^{At} = \begin{bmatrix} \dfrac{e^{2t}+2e^{-t}}{3} + \dfrac{-4(e^{2t}-e^{-t})}{3} & \dfrac{6(e^{2t}-e^{-t})}{3} \\[10pt] \dfrac{-3(e^{2t}-e^{-t})}{3} & \dfrac{e^{2t}+2e^{-t}}{3} + \dfrac{5(e^{2t}-e^{-t})}{3} \end{bmatrix}$$

$$e^{At} = \begin{bmatrix} \dfrac{-3e^{2t}+6e^{-t}}{3} & 2(e^{2t}-e^{-t}) \\[10pt] -(e^{2t}-e^{-t}) & \dfrac{6e^{2t}-e^{-t}}{3} \end{bmatrix} = \begin{bmatrix} -e^{2t}+2e^{-t} & 2e^{2t}-2e^{-t} \\[10pt] -e^{2t}+e^{-t} & 2e^{2t}-e^{-t} \end{bmatrix}$$

### Solução com $X_0 = (3;\,2)$

$$X(t) = e^{At}\begin{pmatrix}3\\2\end{pmatrix}$$

$$x(t) = 3(-e^{2t}+2e^{-t}) + 2(2e^{2t}-2e^{-t}) = e^{2t}+2e^{-t}$$

$$y(t) = 3(-e^{2t}+e^{-t}) + 2(2e^{2t}-e^{-t}) = e^{2t}+e^{-t}$$

$$\boxed{x(t) = e^{2t}+2e^{-t}, \qquad y(t) = e^{2t}+e^{-t}}$$

---

## Item (j) — Sistema $2\times2$

$$\dot{x} + 5x - 12y = 0, \qquad \dot{y} + 2x - 5y = 0, \qquad x(0)=8,\;y(0)=3$$

Reescrevendo:

$$\dot{x} = -5x + 12y, \qquad \dot{y} = -2x + 5y$$

$$A = \begin{bmatrix}-5 & 12\\ -2 & 5\end{bmatrix}$$

### Autovalores

$$\det(A-\lambda I) = (-5-\lambda)(5-\lambda)+24 = \lambda^2-1 = 0$$

$$\lambda_1 = 1, \quad \lambda_2 = -1$$

### $e^{At}$ — Cayley-Hamilton

$$e^{t} = \alpha_0 + \alpha_1, \qquad e^{-t} = \alpha_0 - \alpha_1$$

$$\alpha_1 = \frac{e^{t}-e^{-t}}{2} = \sinh t, \qquad \alpha_0 = \frac{e^{t}+e^{-t}}{2} = \cosh t$$

$$e^{At} = \cosh t\, I + \sinh t\, A = \begin{bmatrix}\cosh t - 5\sinh t & 12\sinh t\\ -2\sinh t & \cosh t + 5\sinh t\end{bmatrix}$$

### Solução com $X_0 = (8;\,3)$

$$x(t) = 8(\cosh t - 5\sinh t) + 3(12\sinh t) = 8\cosh t + (-40+36)\sinh t$$

$$y(t) = 8(-2\sinh t) + 3(\cosh t + 5\sinh t) = 3\cosh t + (-16+15)\sinh t$$

$$\boxed{x(t) = 8\cosh t - 4\sinh t, \qquad y(t) = 3\cosh t - \sinh t}$$

---

## Resumo

| Item | Equação | $\lambda$ | Método | Tipo |
|:---:|:---:|:---:|:---:|:---:|
| (a) | $\ddot{x}+2\dot{x}-8x=0$ | $2,-4$ | $e^{At}X_0$ | Homogênea, $t_0=1$ |
| (b) | $\ddot{x}+2\dot{x}-8x=4$ | $2,-4$ | Variação de par. | Não homog., $t_0=0$ |
| (c) | $\ddot{x}+2\dot{x}-8x=4$ | $2,-4$ | Variação de par. | Não homog., $t_0=1$ |
| (d) | $\ddot{x}+2\dot{x}-8x=4$ | $2,-4$ | $e^{At}X_0$ + part. | Completa |
| (e) | $\ddot{x}+x=0$ | $\pm j$ | Geral | Homogênea |
| (f) | $\ddot{x}+x=0$ | $\pm j$ | $e^{At}X_0$ | CI nulas |
| (g) | $\ddot{x}+x=t$ | $\pm j$ | Variação de par. | Não homog. |
| (h) | $\ddot{y}-\dot{y}-2y=0$ | $2,-1$ | Geral | Homogênea |
| (i) | Sistema $2\times2$ | $2,-1$ | $e^{At}X_0$ | CI $(3,2)$ |
| (j) | Sistema $2\times2$ | $1,-1$ | $e^{At}X_0$ | CI $(8,3)$ |
