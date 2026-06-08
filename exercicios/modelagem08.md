<h1>Modelagem matemática 08</h1>

<img width="647" height="486" alt="image" src="https://github.com/user-attachments/assets/d9ca305c-d49b-4d75-af12-788c5d20324a" />

### (a) Equações diferenciais de segunda ordem

Considerando $$y_1$$ e $$y_2$$ como deslocamentos a partir do equilíbrio (positivos para baixo), as forças nas massas são:

- **Massa $$m_1$$**:  
  Mola $$k_1$$: $$-k_1 y_1$$  
  Amortecedor $$b_1$$: $$-b_1 \dot{y}_1$$  
  Conexão com $$m_2$$ (mola $$k_2$$ e amortecedor $$b_2$$):  
  Força da mola: $$-k_2 (y_1 - y_2)$$  
  Força do amortecedor: $$-b_2 (\dot{y}_1 - \dot{y}_2)$$  
  Força externa: $$u_1(t)$$

- **Massa $$m_2$$**:  
  Mola $$k_3$$: $$-k_3 y_2$$  
  Conexão com $$m_1$$: $$+k_2 (y_1 - y_2) + b_2 (\dot{y}_1 - \dot{y}_2)$$  
  Força externa: $$u_2(t)$$

Assim, as equações são:

$$
\begin{aligned}
m_1 \ddot{y}_1 + (b_1+b_2) \dot{y}_1 - b_2 \dot{y}_2 + (k_1+k_2) y_1 - k_2 y_2 &= u_1(t) \\[4pt]
m_2 \ddot{y}_2 - b_2 \dot{y}_1 + b_2 \dot{y}_2 - k_2 y_1 + (k_2+k_3) y_2 &= u_2(t)
\end{aligned}
$$

---

### (b) Variáveis de estado

Definindo  
$$x_1 = y_1,\; x_2 = y_2,\; x_3 = \dot{y}_1,\; x_4 = \dot{y}_2$$, obtém-se o sistema de primeira ordem:

$$
\begin{cases}
\dot{x}_1 = x_3 \\[4pt]
\dot{x}_2 = x_4 \\[4pt]
\dot{x}_3 = \dfrac{1}{m_1}\Bigl[ u_1 - (b_1+b_2)x_3 + b_2 x_4 - (k_1+k_2)x_1 + k_2 x_2 \Bigr] \\[8pt]
\dot{x}_4 = \dfrac{1}{m_2}\Bigl[ u_2 + b_2 x_3 - b_2 x_4 + k_2 x_1 - (k_2+k_3)x_2 \Bigr]
\end{cases}
$$

---

### (c) Forma vetorial–matricial

Com $$\mathbf{x} = [x_1\; x_2\; x_3\; x_4]^T$$, $$\mathbf{u} = [u_1\; u_2]^T$$ e saída $$\mathbf{y} = [y_1\; y_2]^T$$:

$$
\dot{\mathbf{x}} = A\,\mathbf{x} + B\,\mathbf{u}, \qquad 
\mathbf{y} = C\,\mathbf{x} + D\,\mathbf{u}
$$

onde

$$
A = \begin{bmatrix}
0 & 0 & 1 & 0 \\[2pt]
0 & 0 & 0 & 1 \\[2pt]
-\dfrac{k_1+k_2}{m_1} & \dfrac{k_2}{m_1} & -\dfrac{b_1+b_2}{m_1} & \dfrac{b_2}{m_1} \\[8pt]
\dfrac{k_2}{m_2} & -\dfrac{k_2+k_3}{m_2} & \dfrac{b_2}{m_2} & -\dfrac{b_2}{m_2}
\end{bmatrix},\quad
B = \begin{bmatrix}
0 & 0 \\ 0 & 0 \\ \dfrac{1}{m_1} & 0 \\ 0 & \dfrac{1}{m_2}
\end{bmatrix},
$$

$$
C = \begin{bmatrix}
1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0
\end{bmatrix},\quad
D = \begin{bmatrix}
0 & 0 \\ 0 & 0
\end{bmatrix}.
$$




