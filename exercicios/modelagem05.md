<h1>Modelagem matemática 05</h1>

<img width="239" height="176" alt="image" src="https://github.com/user-attachments/assets/c2f34b40-67f7-432d-8c1f-cdb2eee53f3f" />

Com base na figura (circuito com fonte $$E$$, resistor $$R$$ em série, e dois indutores $$L_1$$ e $$L_2$$ em paralelo, sem capacitores), as correntes são:  
$$i_1$$ no resistor, $$i_2$$ em $$L_1$$, $$i_3$$ em $$L_2$$, com $$i_1 = i_2 + i_3$$.
<p>
### Equações do circuito

- Lei das malhas:  
  $$E = R\,i_1 + v_L$$
  onde $$v_L$$ é a tensão comum sobre os dois indutores.

- Relações dos indutores:  
  $$v_L = L_1 \frac{di_2}{dt} = L_2 \frac{di_3}{dt}$$

- Substituindo $$i_1 = i_2 + i_3$$:
  $$E = R(i_2 + i_3) + v_L$$
  Logo,
  $$v_L = E - R(i_2 + i_3)$$

<p>
### Equações de estado (variáveis: $$i_2$$ e $$i_3$$)
<p>
$$
\frac{di_2}{dt} = \frac{v_L}{L_1} = \frac{1}{L_1}\bigl(E - R(i_2+i_3)\bigr)
= -\frac{R}{L_1} i_2 - \frac{R}{L_1} i_3 + \frac{1}{L_1} E
$$
<p>
$$
\frac{di_3}{dt} = \frac{v_L}{L_2} = \frac{1}{L_2}\bigl(E - R(i_2+i_3)\bigr)
= -\frac{R}{L_2} i_2 - \frac{R}{L_2} i_3 + \frac{1}{L_2} E
$$

<p>
### Matrizes de estado (entrada $$u = E$$)
<p>
$$
\dot{\mathbf{x}} = A\,\mathbf{x} + B\,u,\qquad
\mathbf{x} = \begin{bmatrix} i_2 \\ i_3 \end{bmatrix}
$$
<p>
$$
A = \begin{bmatrix}
-\dfrac{R}{L_1} & -\dfrac{R}{L_1} \\[6pt]
-\dfrac{R}{L_2} & -\dfrac{R}{L_2}
\end{bmatrix},\qquad
B = \begin{bmatrix}
\dfrac{1}{L_1} \\[6pt]
\dfrac{1}{L_2}
\end{bmatrix}
$$


