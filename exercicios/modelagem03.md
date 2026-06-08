<h1>Modelagem matemática 03</h1>

<img width="465" height="146" alt="image" src="https://github.com/user-attachments/assets/a36ad183-e9e9-45a8-8ac9-f041cf4583ad" />

Com base na descrição do sistema mecânico de duas massas (m₁ e m₂) com molas (k₁, k₂, k₃) e amortecedor (b), e força de entrada u aplicada em m₁, as equações do movimento para os deslocamentos w₁ (massa m₁) e w₂ (massa m₂) são:

<p>$$
\begin{aligned}
m_1 \ddot{w}_1 + b (\dot{w}_1 - \dot{w}_2) + (k_1 + k_2) w_1 - k_2 w_2 &= u \\
m_2 \ddot{w}_2 + b (\dot{w}_2 - \dot{w}_1) + (k_2 + k_3) w_2 - k_2 w_1 &= 0
\end{aligned}
$$
<p>
Em forma matricial:

<p>
<p>$$
\begin{bmatrix}
m_1 & 0 \\
0 & m_2
\end{bmatrix}
\begin{bmatrix}
\ddot{w}_1 \\ \ddot{w}_2
\end{bmatrix}
+
\begin{bmatrix}
b & -b \\
-b & b
\end{bmatrix}
\begin{bmatrix}
\dot{w}_1 \\ \dot{w}_2
\end{bmatrix}
+
\begin{bmatrix}
k_1+k_2 & -k_2 \\
-k_2 & k_2+k_3
\end{bmatrix}
\begin{bmatrix}
w_1 \\ w_2
\end{bmatrix}
=
\begin{bmatrix}
u \\ 0
\end{bmatrix}
$$

<p>
Os autovalores dessa matriz determinam a estabilidade do sistema livre. Para valores positivos de \(m_1, m_2, k_1, k_2, k_3, b\), o sistema é **assintoticamente estável** (devido ao amortecedor, a menos que \(b=0\), caso em que pode ser marginalmente estável ou instável dependendo das molas).

<p>$$
\dot{\mathbf{x}} = A\,\mathbf{x} + B\,u,\qquad \mathbf{y} = C\,\mathbf{x} + D\,u
$$

com:

<p>$$
A = \begin{bmatrix}
0 & 0 & 1 & 0 \<p>$$2pt]
0 & 0 & 0 & 1 \<p>$$2pt]
-\dfrac{k_1+k_2}{m_1} & \dfrac{k_2}{m_1} & -\dfrac{b}{m_1} & \dfrac{b}{m_1} \<p>$$6pt]
\dfrac{k_2}{m_2} & -\dfrac{k_2+k_3}{m_2} & \dfrac{b}{m_2} & -\dfrac{b}{m_2}
\end{bmatrix},\qquad
B = \begin{bmatrix} 0 \\ 0 \\ \dfrac{1}{m_1} \\ 0 \end{bmatrix},
$$

<p>$$
C = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \end{bmatrix},\qquad
D = \begin{bmatrix} 0 \\ 0 \end{bmatrix}.
$$
<p>
Estas matrizes representam o modelo linear de espaço de estados do sistema massa-mola-amortecedor com dois graus de liberdade.
