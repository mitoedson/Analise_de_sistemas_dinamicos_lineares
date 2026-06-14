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
  $\lambda_1=5$: $k_1=(1,2)$  
  $\lambda_2=-1$: $k_2=(1,-1)$
- **Estabilidade:** instável (sela, autovalores de sinais opostos).
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,2) e^{5t} + c_2(1,-1)e^{-t} $$

<hr>

<p><b>(b)</b>
<p>$\frac{dx}{dt}=2x+2y \quad \frac{dy}{dt}=x+3y$
<p>
Portanto, 
<p>
$$A=\begin{bmatrix}2&2\\1&3\end{bmatrix}$$
  
- **Autovalores:** $\lambda_1=4\; \lambda_2=1$
- **Autovetores:**  
  $\lambda_1=4$: $k_1=(1,1)$  
  $\lambda_2=1$: $k_2=(1,-0.5)$
- **Estabilidade:** instável (nó repulsivo, ambos positivos).
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,1) e^{4t} + c_2(1,-0.5)e^{t} $$

<hr>
<p><b>(c)</b>
<p>$\frac{dx}{dt}=-4x+2y \quad \frac{dy}{dt}=-\frac{5}{2}x+2y $
<p>
Portanto, 
<p>
$$A=\begin{bmatrix}-4&2\\ -\frac{5}{2}&2\end{bmatrix}$$

- **Autovalores:** $\lambda_1=1\; \lambda_2=-3$
- **Autovetores:**  
  $\lambda_1=1$: $k_1=(1,\frac{5}{2})$  
  $\lambda_2=-3$: $k_2=(1,\frac{1}{2})$
- **Estabilidade:** instável (sela).
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,\frac{5}{2}) e^{t} + c_2(1,\frac{1}{2})e^{-3t} $$

<hr>
<p><b>(d)</b>
<p>$\frac{dx}{dt}=-\frac{5}{2}x+2y\quad \frac{dy}{dt}=\frac{3}{4}x-2y $
<p>
Portanto, 
<p>
$$ A=\begin{bmatrix} -\frac{5}{2}&2\\ \frac{3}{4}&-2\end{bmatrix} $$

- **Autovalores:** $\lambda_1=-1\; \lambda_2=-\frac{7}{2}$
- **Autovetores:**  
  $\lambda_1=-1$: $k_1=(1,\frac{3}{4})$  
  $\lambda_2=-\frac{7}{2}$: $k_2=(1,-\frac{1}{2})$
- **Estabilidade:** assintoticamente estável (nó atrator, ambos negativos).
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,\frac{3}{4}) e^{-t} + c_2(1,-\frac{1}{2})e^{-\frac{7}{2}t} $$

<hr>
<p><b>(e)</b>
<p>$$ X' = \begin{bmatrix} 10&-5 \\ 8&-12 \end{bmatrix}X $$

- **Autovalores:** $\lambda_1=-10\; \lambda_2=8$
- **Autovetores:**  
  $\lambda_1=-10$: $k_1=(1,4)$  
  $\lambda_2=8$: $k_2=(1,\frac{2}{5})$
- **Estabilidade:** instável (sela).
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,4) e^{10t} + c_2(1,\frac{2}{5})e^{-8t} $$

<hr>
<p><b>(f)</b>
<p>$$ X' = \begin{bmatrix} -6&2 \\ -3&1 \end{bmatrix}X $$

- **Autovalores:** $\lambda_1=0\; \lambda_2=-5$
- **Autovetores:**  
  $\lambda_1=0$: $k_1=(1,3)$  
  $\lambda_2=-5$: $k_2=(1,\frac{1}{2})$
- **Estabilidade:** estável (marginalmente), pois um autovalor é nulo e o outro negativo.
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,3) + c_2(1,\frac{1}{2})e^{-5t} $$
<p>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/0c17d70f-a667-41e0-b3d9-01ef19ec0e51" />
<p>
<b>Retrato de fase:</b> comportamento singular — existe uma **linha inteira de equilíbrios** na direção de $k_1 = (1;\,3)$ (pois $e^{0 \cdot t} = 1$, constante). O modo $e^{-5t}$ decai rapidamente para zero, fazendo todas as trajetórias convergirem para um ponto **na reta** $x_2 = 3x_1$, não necessariamente para a origem. O ponto de chegada depende de $c_1$, ou seja, da condição inicial.
<p><b>Resposta temporal:</b> $x_1(t)$ e $x_2(t)$ decaem rapidamente do valor inicial até um **patamar não nulo** (determinado por $c_1$), e depois permanecem constantes. A constante final é diferente para cada condição inicial.
<p>
<b>Classificação:</b> Marginalmente estável — linha de equilíbrios (autovalor nulo simples com autovalor negativo).
<p>
<b>Diferença em relação ao caso repetido (R-a):</b> lá, $\lambda = 0$ era repetido e havia crescimento linear. Aqui, $\lambda = 0$ é simples e o outro autovalor é negativo — o sistema estabiliza em um patamar, não cresce.

<hr>
## Resumo Geral

| Fig. | $A$ | $\lambda_1$ | $\lambda_2$ | Retrato de fase | Resposta temporal | Estabilidade |
|:----:|:---:|:-----------:|:-----------:|:---------------:|:-----------------:|:------------:|
| (a) | $[1,2;4,3]$ | $+5$ | $-1$ | Ponto de sela | Divergência após transiente | **Instável** |
| (b) | $[2,2;1,3]$ | $+4$ | $+1$ | Nó repulsor | Crescimento exponencial | **Instável** |
| (c) | $[-4,2;-\frac{5}{2},2]$ | $+1$ | $-3$ | Ponto de sela | Divergência após transiente | **Instável** |
| (d) | $[-\frac{5}{2},2;\frac{3}{4},-2]$ | $-1$ | $-7/2$ | Nó atrator | Decaimento com dobra | **Assim. estável** |
| (e) | $[10,-5;8,-12]$ | $+8$ | $-10$ | Ponto de sela (agudo) | Divergência rápida | **Instável** |
| (f) | $[-6,2;-3,1]$ | $0$ | $-5$ | Linha de equilíbrios | Convergência a patamar | **Marg. estável** |




