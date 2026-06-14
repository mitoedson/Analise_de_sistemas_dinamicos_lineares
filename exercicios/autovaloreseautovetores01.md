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
<p>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/063c5b6b-f26e-4ee1-8cf7-3213393a41ea" />
<p>
<b>Retrato de fase:</b> padrão de ponto de sela. Existem duas direções especiais (as dos autovetores):
<ul>
  <li>Na direção de $k_2 = (1;\,-1)$: trajetórias convergem para a origem (modo estável, $\lambda_2 = -1$). Quando  $\lambda < 0$, as trajetórias convergem.
  <li>Na direção de $k_1 = (1;\;2)$: trajetórias divergem da origem (modo instável, $\lambda_1 = 5$). Quando  $\lambda > 0$, as trajetórias divergem.
  <li>Todas as demais trajetórias chegam perto da origem e depois são "arremessadas" para longe, curvando-se na direção de $k_1$.
</ul>
<p>
<b>Resposta temporal:</b> para $t$ pequeno, pode haver decaimento transitório (influência de $e^{-t}$); a longo prazo, $e^{5t}$ domina completamente e as curvas divergem.
<p>
<b>Classificação:</b> Instável — ponto de sela (autovalores de sinais opostos).

  

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
<p>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/8f611b68-2fe9-41d8-bc21-2acbd96e0bde" />
<p>
<b>Retrato de fase:</b> padrão de nó repulsor. Todas as trajetórias divergem da origem. Para $t$ grande, o termo $e^{4t}$ domina e as curvas se alinham com a direção de $k_1 = (1;\,1)$. Para $t$ negativo (ou perto da origem), a influência de $e^{t}$ aparece, curvando as trajetórias.
<p>Resposta temporal:</b> ambas as componentes crescem exponencialmente. O crescimento de $x_1(t)$ e $x_2(t)$ se torna paralelo a longo prazo (dominância de $e^{4t}$).
<p>
<b>Classificação:</b> Instável — nó repulsor (ambos os autovalores positivos).

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
<p>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/cd984f65-d692-4e49-b23d-9dfd09484c81" />
<p>
<b>Retrato de fase:</b> outro **ponto de sela**, mas com geometria diferente de (a). A direção estável é $k_2 = (1;\,1/2)$ (trajetórias que partem nessa direção convergem para a origem) e a instável é $k_1 = (1;\,5/2)$. O modo estável decai 3× mais rápido que em (a), então as curvas se alinham mais rapidamente com a direção instável.
<p>
<b>Resposta temporal:</b> decaimento inicial transitório de $e^{-3t}$, seguido de divergência dominada por $e^{t}$.
<p>
<b>Classificação:</b> Instável — ponto de sela (autovalores de sinais opostos).
 
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
<p>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/3e7fe610-fdd3-4ec1-a824-930992b2f9d2" />
<p>
<b>Retrato de fase:</b> padrão de nó atrator. Todas as trajetórias convergem para a origem. O modo rápido $e^{-7t/2}$ decai primeiro, fazendo as curvas se alinharem com a direção do modo lento $k_1 = (1;\frac{3}{4})$ antes de chegarem à origem. Essa "dobra" das trajetórias é a assinatura visual de um nó com dois autovalores negativos distintos.
<p><b>Resposta temporal:</b> ambas as componentes decaem para zero. Pode haver mudança de curvatura no transiente enquanto o modo rápido $e^{-7t/2}$ se extingue e o modo lento $e^{-t}$ passa a dominar.
<p>
<b>Classificação:</b> Assintoticamente estável — nó atrator (ambos os autovalores negativos).

<hr>
<p><b>(e)</b>
<p>$$ X' = \begin{bmatrix} 10&-5 \\ 8&-12 \end{bmatrix}X $$

- **Autovalores:** $\lambda_1=-10\; \lambda_2=8$
- **Autovetores:**  
  $\lambda_1=-10$: $k_1=(1,4)$  
  $\lambda_2=8$: $k_2=(1,\frac{2}{5})$
- **Estabilidade:** instável (sela).
- **Solução geral** para autovalores reais distintos: $$X'= c_1 (1,4) e^{10t} + c_2(1,\frac{2}{5})e^{-8t} $$
<p>
<img width="600" alt="image" src="https://github.com/user-attachments/assets/0f5a8f95-cd7d-4de8-adb3-8f546cfa9eca" />
<p>
<b>Retrato de fase:</b> ponto de sela com a maior separação entre autovalores de todos os exercícios ($\Delta\lambda = 18$). O modo estável $e^{-10t}$ decai extremamente rápido, de modo que as trajetórias se "endireitam" quase imediatamente na direção instável $k_1 = (1;\frac{2}{5})$. As curvas parecem quase retas divergindo nessa direção.
<p>
<b>Resposta temporal:</b> o transitório estável desaparece muito rapidamente (escala de $\frac{1}{10} = 0.1\ \mathrm{s}$) e a divergência de $e^{8t}$ domina. O intervalo plotado é curto ($t \in [0, 0.8]$).
<p>
<b>Classificação:</b> Instável — ponto de sela.

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




