# Matriz exponencial

<b>(a)</b> 
$\ddot{x} + 2\dot{x} - 8x = 0,\ x(1)=1,\ \dot{x}(1)=0$

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
$\begin{cases}
c_1\cos1 + c_2\sin1 + 1 = 0 \\
-c_1\sin1 + c_2\cos1 + 1 = 1
\end{cases}
\Rightarrow
\begin{cases}
c_1\cos1 + c_2\sin1 = -1 \\
-c_1\sin1 + c_2\cos1 = 0
\end{cases}$  
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




