<h1>Modelagem matemática 09</h1>

<img width="735" height="440" alt="image" src="https://github.com/user-attachments/assets/d48d43bf-9925-4234-991a-9d478e38093f" />

### (a) Equações diferenciais de segunda ordem

Considerando $$y_1$$ e $$y_2$$ como deslocamentos para a direita a partir do equilíbrio, e as forças externas $$u_1$$ (aplicada em $$m_1$$ para a direita) e $$u_2$$ (aplicada em $$m_2$$ para a esquerda, ou seja, força negativa na direção positiva), as equações são:

$$
\begin{aligned}
m_1 \ddot{y}_1 + (b_1+b_2+b)\,\dot{y}_1 - b_2\,\dot{y}_2 + (k_1+k_2)\,y_1 - k_2\,y_2 &= u_1(t) \\\\[4pt]
m_2 \ddot{y}_2 - b_2\,\dot{y}_1 + (b_2+b_3+b)\,\dot{y}_2 - k_2\,y_1 + (k_2+k_3)\,y_2 &= u_2(t)
\end{aligned}
$$

onde $$b$$ é o coeficiente de atrito viscoso com o chão.

---

### (b) Variáveis de estado

Definindo  
$$x_1 = y_1,\; x_2 = y_2,\; x_3 = \dot{y}_1,\; x_4 = \dot{y}_2$$, obtém-se o sistema de primeira ordem:

$$
\begin{cases}
\dot{x}_1 = x_3 \\\\[4pt]
\dot{x}_2 = x_4 \\\\[4pt]
\dot{x}_3 = \dfrac{1}{m_1}\Bigl[ u_1 - (b_1+b_2+b)x_3 + b_2 x_4 - (k_1+k_2)x_1 + k_2 x_2 \Bigr] \\\\[8pt]
\dot{x}_4 = \dfrac{1}{m_2}\Bigl[ u_2 + b_2 x_3 - (b_2+b_3+b)x_4 + k_2 x_1 - (k_2+k_3)x_2 \Bigr]
\end{cases}
$$

---

### (c) Forma vetorial–matricial

Com $$\mathbf{x}=[x_1\;x_2\;x_3\;x_4]^T$$, entradas $$\mathbf{u}=[u_1\;u_2]^T$$ e saídas $$\mathbf{y}=[y_1\;y_2]^T$$:

$$
\dot{\mathbf{x}} = A\,\mathbf{x} + B\,\mathbf{u},\qquad 
\mathbf{y} = C\,\mathbf{x} + D\,\mathbf{u}
$$

onde

$$
A = \begin{bmatrix}
0 & 0 & 1 & 0 \\\\[2pt]
0 & 0 & 0 & 1 \\\\[6pt]
-\dfrac{k_1+k_2}{m_1} & \dfrac{k_2}{m_1} & -\dfrac{b_1+b_2+b}{m_1} & \dfrac{b_2}{m_1} \\\\[10pt]
\dfrac{k_2}{m_2} & -\dfrac{k_2+k_3}{m_2} & \dfrac{b_2}{m_2} & -\dfrac{b_2+b_3+b}{m_2}
\end{bmatrix},\quad
B = \begin{bmatrix}
0 & 0 \\\\[2pt] 0 & 0 \\\\[2pt] \dfrac{1}{m_1} & 0 \\\\[6pt] 0 & \dfrac{1}{m_2}
\end{bmatrix},
$$

$$
C = \begin{bmatrix}
1 & 0 & 0 & 0 \\\\[2pt] 0 & 1 & 0 & 0
\end{bmatrix},\quad
D = \begin{bmatrix}
0 & 0 \\\\[2pt] 0 & 0
\end{bmatrix}.
$$




