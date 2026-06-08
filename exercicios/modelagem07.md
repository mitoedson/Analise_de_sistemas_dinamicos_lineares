<h1>Modelagem matemática 07</h1>

<img width="350" height="252" alt="image" src="https://github.com/user-attachments/assets/b867005d-e5e3-4064-8eb0-db66cba9d755" />

<p>
Com base na descrição do circuito: fonte E, indutor L em série, seguido de um nó que se divide em dois ramos paralelos: um com resistor R (corrente $$i_2$$) e outro com capacitor C (corrente $$i_3$$), com $$i_1 = i_2 + i_3$$. Escolhendo como variáveis de estado as correntes $$i_2$$ e $$i_3$$, obtém-se o seguinte sistema de equações diferenciais lineares de primeira ordem:
<p>
$$
\begin{aligned}
\frac{di_2}{dt} &= \frac{1}{RC}\, i_3 \\[6pt]
\frac{di_3}{dt} &= -\frac{R}{L}\, i_2 - \frac{1}{RC}\, i_3 + \frac{1}{L}\, E
\end{aligned}
$$
<p>
Na forma matricial \(\dot{\mathbf{x}} = A\mathbf{x} + B\mathbf{u}\), com \(\mathbf{x} = \begin{bmatrix} i_2 \\ i_3 \end{bmatrix}\) e \(\mathbf{u} = E\):
<p>
$$
\boxed{
A = \begin{bmatrix}
0 & \dfrac{1}{RC} \\[8pt]
-\dfrac{R}{L} & -\dfrac{1}{RC}
\end{bmatrix}, \qquad
B = \begin{bmatrix}
0 \\[4pt] \dfrac{1}{L}
\end{bmatrix}
}
$$

Estas são as matrizes de estado pedidas, utilizando as correntes $$i_2$$ e $$i_3$$ como variáveis de estado.
