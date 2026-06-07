<h1>Autovalores, Autovetores e Estabilidade - Exercícios</h1>

Para cada sistema \(X' = A X\), determinamos autovalores \(\lambda\) e autovetores \(v\) resolvendo \(\det(A - \lambda I)=0\) e \((A - \lambda I)v = 0\). A estabilidade do ponto de equilíbrio na origem é analisada pelos sinais das partes reais dos autovalores:

- **Assintoticamente estável** se todos \(\operatorname{Re}(\lambda) < 0\).
- **Instável** se algum \(\operatorname{Re}(\lambda) > 0\).
- **Estável (marginalmente)** se \(\operatorname{Re}(\lambda) \le 0\) e pelo menos um \(\operatorname{Re}(\lambda)=0\) sem autovalores com parte real positiva.

## (a)
$$
\frac{dx}{dt}=x+2y,\quad \frac{dy}{dt}=4x+3y \;\Rightarrow\; A=\begin{bmatrix}1&2\\4&3\end{bmatrix}
$$
- **Autovalores:** \(\lambda_1=5,\; \lambda_2=-1\)
- **Autovetores:** \(\lambda_1=5\): \(v_1=(1,2)\); \(\lambda_2=-1\): \(v_2=(1,-1)\)
- **Estabilidade:** instável (sela, autovalores de sinais opostos).

## (b)
$$
\frac{dx}{dt}=2x+2y,\quad \frac{dy}{dt}=x+3y \;\Rightarrow\; A=\begin{bmatrix}2&2\\1&3\end{bmatrix}
$$
- **Autovalores:** \(\lambda_1=4,\; \lambda_2=1\)
- **Autovetores:** \(\lambda_1=4\): \(v_1=(1,1)\); \(\lambda_2=1\): \(v_2=(-2,1)\) (ou \((2,-1)\))
- **Estabilidade:** instável (nó repulsivo, ambos positivos).

## (c)
$$
\frac{dx}{dt}=-4x+2y,\quad \frac{dy}{dt}=-\frac{5}{2}x+2y \;\Rightarrow\; A=\begin{bmatrix}-4&2\\-5/2&2\end{bmatrix}
$$
- **Autovalores:** \(\lambda_1=1,\; \lambda_2=-3\)
- **Autovetores:** \(\lambda_1=1\): \(v_1=(2,5)\); \(\lambda_2=-3\): \(v_2=(2,1)\)
- **Estabilidade:** instável (sela).

## (d)
$$
\frac{dx}{dt}=-\frac{5}{2}x+2y,\quad \frac{dy}{dt}=\frac{3}{4}x-2y \;\Rightarrow\; A=\begin{bmatrix}-5/2&2\\3/4&-2\end{bmatrix}
$$
- **Autovalores:** \(\lambda_1=-1,\; \lambda_2=-\frac{7}{2}=-3.5\)
- **Autovetores:** \(\lambda_1=-1\): \(v_1=(4,3)\); \(\lambda_2=-3.5\): \(v_2=(-2,1)\) (ou \((2,-1)\))
- **Estabilidade:** assintoticamente estável (nó atrator, ambos negativos).

## (e)
$$
X' = \begin{bmatrix}10&-5\\8&-12\end{bmatrix}X
$$
- **Autovalores:** \(\lambda_1=8,\; \lambda_2=-10\)
- **Autovetores:** \(\lambda_1=8\): \(v_1=(5,2)\); \(\lambda_2=-10\): \(v_2=(1,4)\)
- **Estabilidade:** instável (sela).

## (f)
$$
X' = \begin{bmatrix}-6&2\\-3&1\end{bmatrix}X
$$
- **Autovalores:** \(\lambda_1=0,\; \lambda_2=-5\)
- **Autovetores:** \(\lambda_1=0\): \(v_1=(1,3)\); \(\lambda_2=-5\): \(v_2=(2,1)\)
- **Estabilidade:** estável (marginalmente), pois um autovalor é nulo e o outro negativo.









