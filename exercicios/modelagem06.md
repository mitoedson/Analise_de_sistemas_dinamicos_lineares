<h1>Modelagem matemática 06</h1>

<img width="332" height="231" alt="image" src="https://github.com/user-attachments/assets/4b453b4d-b254-4769-ad8d-ad104db70d8a" />

Com base na descrição do circuito (fonte E), indutor (L) em série, divisor em dois ramos paralelos: um com resistor $$R_1$$ 
(corrente $$i_2$$ e outro com resistor $$R_2$$ em série com capacitor $$C$$ (corrente $$i_3$$, com $$i_1 = i_2 + i_3$$), e escolhendo como 
variáveis de estado as correntes $$i_2$$ e $$i_3$$, obtém-se o seguinte sistema de equações diferenciais lineares de primeira ordem:
<p>
$$
\begin{aligned}
\frac{di_2}{dt} &= -\frac{R_1 R_2}{L(R_1+R_2)}\, i_2 + \frac{1}{C(R_1+R_2)}\, i_3 + \frac{R_2}{L(R_1+R_2)}\, E \\[pt]
\frac{di_3}{dt} &= -\frac{R_1^2}{L(R_1+R_2)}\, i_2 - \frac{1}{C(R_1+R_2)}\, i_3 + \frac{R_1}{L(R_1+R_2)}\, E
\end{aligned}
$$
<p>
Na forma matricial $$\dot{\mathbf{x}} = A\mathbf{x} + B\mathbf{u}\),
com \(\mathbf{x} = \begin{bmatrix} i_2 \\ i_3 \end{bmatrix}\) e \(\mathbf{u} = E\):
$$
<p>
$$\boxed{A = \begin{bmatrix}
-\dfrac{R_1 R_2}{L(R_1+R_2)} & \dfrac{1}{C(R_1+R_2)} \\[8pt]
-\dfrac{R_1^2}{L(R_1+R_2)} & -\dfrac{1}{C(R_1+R_2)}
\end{bmatrix}, \qquad
B = \begin{bmatrix}
\dfrac{R_2}{L(R_1+R_2)} \\[8pt]
\dfrac{R_1}{L(R_1+R_2)}
\end{bmatrix}
}
$$

Estas são as matrizes de estado pedidas, com as variáveis sendo as correntes \(i_2\) e \(i_3\).
