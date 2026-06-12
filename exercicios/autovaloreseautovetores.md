<h1>Autovalores, Autovetores e Estabilidade - Exercícios</h1>

Para cada sistema $X' = A X$, determinamos os autovalores $\lambda$ e autovetores $v$ resolvendo $\det(A - \lambda I)=0$ e $(A - \lambda I)v = 0$. A estabilidade do ponto de equilíbrio na origem é analisada pelos sinais das partes reais dos autovalores:

- **Assintoticamente estável** se todos $\mathrm{Re}(\lambda) < 0$.
- **Instável** se algum $\mathrm{Re}(\lambda) > 0$.
- **Estável (marginalmente)** se $\mathrm{Re}(\lambda) \le 0$ e pelo menos um $\mathrm{Re}(\lambda)=0$ sem autovalores com parte real positiva.
<p><a href="/teoria/autovaloreseautovetores.md">Ver teoria</a>

<p><b>(a)</b>
<p>
$\frac{dx}{dt}=x+2y \quad \frac{dy}{dt}=4x+3y$
<p>
Portanto, 
<p>
$$A = \begin{pmatrix}
1 & 2 \\
4 & 3
\end{pmatrix}$$

- **Autovalores:** $\lambda_1=5\; \lambda_2=-1$
- **Autovetores:**  
  $\lambda_1=5$: $v_1=(1,2)$  
  $\lambda_2=-1$: $v_2=(1,-1)$
- **Estabilidade:** instável (sela, autovalores de sinais opostos).
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,2) e^{4t} + c_2(1,-1)e^{t} $$


<p align="center">
<img width="400" align="center" alt="image" src="https://github.com/user-attachments/assets/4a14555e-4477-4d83-a0d6-c28a37a66490" />

<hr>

<p><b>(b)</b>
<p>$$ \frac{dx}{dt}=2x+2y,\quad \frac{dy}{dt}=x+3y$$
<p>
Portanto, 
<p>
$$A=\begin{bmatrix}2&2\\1&3\end{bmatrix}$$
  
- **Autovalores:** $\lambda_1=4\; \lambda_2=1$
- **Autovetores:**  
  $\lambda_1=4$: $v_1=(1,1)$  
  $\lambda_2=1$: $v_2=(-2,1)$ (ou $(2,-1)$)
- **Estabilidade:** instável (nó repulsivo, ambos positivos).

<p><b>(c)</b>
<p>$$ \frac{dx}{dt}=-4x+2y,\quad \frac{dy}{dt}=-\frac{5}{2}x+2y $$
<p>
Portanto, 
<p>
$$A=\begin{bmatrix}-4&2\\ \frac{5}{2}&2\end{bmatrix}$$

- **Autovalores:** $\lambda_1=1\; \lambda_2=-3$
- **Autovetores:**  
  $\lambda_1=1$: $v_1=(2,5)$  
  $\lambda_2=-3$: $v_2=(2,1)$
- **Estabilidade:** instável (sela).

<p><b>(d)</b>
<p>$$ \frac{dx}{dt}=-\frac{5}{2}x+2y,\quad \frac{dy}{dt}=\frac{3}{4}x-2y $$
<p>
Portanto, 
<p>
$$ A=\begin{bmatrix} \frac{5}{2}&2\\ \frac{5}{2}&-2\end{bmatrix} $$

- **Autovalores:** $\lambda_1=-1\; \lambda_2=-\frac{7}{2}=-3.5$
- **Autovetores:**  
  $\lambda_1=-1$: $v_1=(4,3)$  
  $\lambda_2=-3.5$: $v_2=(-2,1)$ (ou $(2,-1)$)
- **Estabilidade:** assintoticamente estável (nó atrator, ambos negativos).

<p><b>(e)</b>
<p>$$ X' = \begin{bmatrix} 10&-5 \\ 8&-12 \end{bmatrix}X $$

- **Autovalores:** $\lambda_1=8\; \lambda_2=-10$
- **Autovetores:**  
  $\lambda_1=8$: $v_1=(5,2)$  
  $\lambda_2=-10$: $v_2=(1,4)$
- **Estabilidade:** instável (sela).

<p><b>(f)</b>
<p>$$ X' = \begin{bmatrix} -6&2 \\ -3&1 \end{bmatrix}X $$

- **Autovalores:** $\lambda_1=0\; \lambda_2=-5$
- **Autovetores:**  
  $\lambda_1=0$: $v_1=(1,3)$  
  $\lambda_2=-5$: $v_2=(2,1)$
- **Estabilidade:** estável (marginalmente), pois um autovalor é nulo e o outro negativo.









