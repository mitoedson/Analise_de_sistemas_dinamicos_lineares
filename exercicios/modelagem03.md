<h1>Modelagem matemática 03</h1>

<img width="465" height="146" alt="image" src="https://github.com/user-attachments/assets/a36ad183-e9e9-45a8-8ac9-f041cf4583ad" />

Com base na descrição do sistema mecânico de duas massas (m₁ e m₂) com molas (k₁, k₂, k₃) e amortecedor (b), e força de entrada u aplicada em m₁, as equações do movimento para os deslocamentos w₁ (massa m₁) e w₂ (massa m₂) são:
<p>
- <b>Convenção adotada:</b>  
  Os deslocamentos $$w_1$$ e $$w_2$$ são medidos a partir das posições de equilíbrio estático (com molas relaxadas).  
  Sentido positivo: para a direita (mesmo da força de entrada $$u$$ aplicada em $$m_1$$.

- **Força da mola $$k_2$$ entre as massas**:  
  O alongamento relativo é $$w_2 - w_1$$.  
  - Se $$w_2 - w_1 > 0$$ (mola esticada), a mola puxa $$m_1$$ para a direita (força $$+k_2(w_2-w_1)$$) e puxa $$m_2$$ para a esquerda (força $$-k_2(w_2-w_1)$$).  
  - Se $$w_2 - w_1 < 0$$ (mola comprimida), a mola empurra $$m_1$$ para a esquerda (força $$-k_2(w_1-w_2)$$) e empurra $$m_2$$ para a direita (força $$+k_2(w_1-w_2)$$).  
  Isso é exatamente o que aparece nas equações: em $$m_1$$, o termo é $$-k_2(w_1-w_2)$$; em $$m_2$$, é $$+k_2(w_1-w_2)$$.

- **Força do amortecedor \(b\)**:  
  Age com sinal oposto à velocidade relativa.  
  Para $$m_1$$: $$-b(\dot{w}_1 - \dot{w}_2)$$; para $$m_2$$: $$-b(\dot{w}_2 - \dot{w}_1) = +b(\dot{w}_1 - \dot{w}_2)$$.

- **Forças das molas das paredes**:  
  - $$k_1$$ (esquerda): puxa $$m_1$$ para a esquerda quando esticada $$(w_1>0$$), ou empurra para a direita quando comprimida $$(w_1<0$$): força $$-k_1 w_1$$.  
  - $$k_3$$ (direita): puxa $$m_2$$ para a direita quando esticada $$(w_2<0$$? Cuidado: o ponto fixo da direita está em $$w=0$$? Normalmente, consideramos que as posições de equilíbrio são com molas relaxadas, então se $$m_2$$ se desloca para a direita $$(w_2>0$$), a mola $$k_3$$ é comprimida e empurra $$m_2$$ para a esquerda: força $$-k_3 w_2$$. Se $$w_2<0$$, a mola está esticada e puxa para a direita: $$+k_3|w_2|$$, que é $$-k_3 w_2$$ (pois $$w_2$$ negativo). Portanto, o termo é $$-k_3 w_2$$.

Assim, as equações de movimento estão consistentes com a sua observação:  
- **Mola comprimida** \(\Rightarrow\) força que tende a afastar as massas (direcionada para fora).  
- **Mola esticada** \(\Rightarrow\) força que tende a aproximar as massas (direcionada para dentro).  

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
Os autovalores dessa matriz determinam a estabilidade do sistema livre. Para valores positivos de $$m_1, m_2, k_1, k_2, k_3, b$$, o sistema <b>assintoticamente estável</b> (devido ao amortecedor, a menos que $$b=0$$, caso em que pode ser marginalmente estável ou instável dependendo das molas).

<p>$$
\dot{\mathbf{x}} = A\,\mathbf{x} + B\,u,\qquad \mathbf{y} = C\,\mathbf{x} + D\,u
$$
<p>
com:

<p>$$
A = \begin{bmatrix} 0 & 0 & 1 & 0 \\[2pt]
0 & 0 & 0 & 1 \\[2pt]
-\dfrac{k_1+k_2}{m_1} & \dfrac{k_2}{m_1} & -\dfrac{b}{m_1} & \dfrac{b}{m_1} \\[6pt]
\dfrac{k_2}{m_2} & -\dfrac{k_2+k_3}{m_2} & \dfrac{b}{m_2} & -\dfrac{b}{m_2} \end{bmatrix},\qquad
B = \begin{bmatrix} 0 \\ 0 \\ \dfrac{1}{m_1} \\ 0 \end{bmatrix},
$$

<p>$$
C = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \end{bmatrix},\qquad
D = \begin{bmatrix} 0 \\ 0 \end{bmatrix}.
$$
<p>
Estas matrizes representam o modelo linear de espaço de estados do sistema massa-mola-amortecedor com dois graus de liberdade.
