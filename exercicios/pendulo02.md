<h1>Pêndulo amortecido</h1>

O pêndulo amortecido é descrito por

$$\dot x = y, \dot y = −ω^2 sin(x) - γy$$, com ω > 0 e γ ≥ 0.

(a) Encontre os pontos de equilíbrio.

(b) Calcule a matriz Jacobiana J(x, y).

(c) Linearize o sistema em (0, 0) e em (π, 0).

(d) Para ω = 2 e γ = 0,6, classifique os dois equilíbrios.

---

(a)
### Pontos de equilíbrio

<!-- Obs.: 
\begin{case} coloco as chaves para sistemas lineares, \in\mathbb{Z} indico pertence a conjunto de números inteiros 
-->

```math
\begin{cases} \dot x = 0 \\ \dot y = 0\end{cases} \Rightarrow \begin{cases}y=0 \\ -\omega^2 \sin(x) - \gamma y=0\end{cases}
\Rightarrow \begin{cases} y=0 \qquad(a)\\ sin(x) = -\frac{\gamma y }{\omega^2} \qquad(b)\end{cases}
```

Substituíndo y = 0 em (b), sabendo que ω > 0  e γ ≥ 0:

```math
\sin(x) = -\frac{\gamma (0) }{\omega^2} = 0 \Rightarrow \begin{cases} y=0 \\ x = n\pi,\quad n\in\mathbb{Z} \end{cases}
```

### Matriz Jacobiana

```math
\begin{cases} f_1(x,y) = y \\ f_2(x,y) = −ω^2 sin(x) - γy \end{cases}
```


```math
J(x,y)=\begin{bmatrix} \frac{\partial f_1}{\partial x} & \frac{\partial f_1}{\partial y} \\ \frac{\partial f_2}{\partial x} & \frac{\partial f_2}{\partial y} \end{bmatrix}
=\begin{bmatrix} \frac{\partial y}{\partial x} & \frac{\partial y}{\partial y} \\ \frac{\partial −ω^2 sin(x) - γy}{\partial x} & \frac{\partial −ω^2 sin(x) - γy}{\partial y} \end{bmatrix}
=\begin{bmatrix} 0 & 1 \\ −ω^2 cos(x) & - γ \end{bmatrix}
```

### Linearização nos pontos de equilíbrio

#### Em (0,0):
```math
J(x,y)=\begin{bmatrix} 0 & 1 \\ −ω^2 cos(0) & - γ \end{bmatrix}=\begin{bmatrix} 0 & 1 \\ −ω^2 & - γ \end{bmatrix}
```
```math
T=0+(-γ)=-γ , D=det(J(x,y)=(0)(-γ)-(1)(−ω^2)=ω^2
```
O polinômio caractrístico para (0,0):
```math
\lambda^2+γ\lambda+ω^2=0
```

#### Em ($\pi$,0):
```math
J(x,y)=\begin{bmatrix} 0 & 1 \\ −ω^2 cos(\pi) & - γ \end{bmatrix}=\begin{bmatrix} 0 & 1 \\ ω^2 & - γ \end{bmatrix}
```
```math
T=0+(-γ)=-γ , D=det(J(x,y)=(0)(-γ)-(1)(ω^2)=-ω^2
```
O polinômio caractrístico para (0,0):
```math
\lambda^2+γ\lambda-ω^2=0 
```

### Classificando para ω = 2 e γ = 0,6:

#### Em (0,0):
```math
\lambda^2+0,6\lambda+(2)^2=0 \Rightarrow \lambda = \frac{-0,6 \pm i\sqrt{15,64}}{2}
```
Como Re{$\lambda$}<0, (0,0) é foco assintoticamente estável.

#### Em ($\pi$,0):
```math
\lambda^2+0,6\lambda-(2)^2=0 \Rightarrow \lambda = \frac{-0,6 \pm \sqrt{16,36}}{2}
```
($\pi$,0) é instável (ponto de sela).


