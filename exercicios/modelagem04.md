<h1>Modelagem matemática 04</h1>

<img width="240" height="187" alt="image" src="https://github.com/user-attachments/assets/6b856c16-7f3f-4a85-a951-e2ad355d2eff" />

O circuito descrito possui uma fonte de tensão $$E$$, um resistor $$R_1$$ em série com uma associação paralela composta por um capacitor $$C$$ e um ramo série $$R_2$$-L. As correntes são: $$i_1$$ (através de $$R_1$$), $$i_2$$ (através do capacitor) e $$i_3$$ (através do indutor e de $$R_2$$), com $$i_1 = i_2 + i_3$$. As variáveis de estado naturais são a tensão $$v$$ sobre o capacitor (e sobre o paralelo) e a corrente $$i_3$$ no indutor.

Aplicando as leis de Kirchhoff:

- Na malha da fonte: $$E = R_1 i_1 + v$$.
- No nó: $$i_1 = i_2 + i_3$$.
- No capacitor: $$i_2 = C \frac{dv}{dt}$$.
- No ramo $$R_2$$-L: $$v = R_2 i_3 + L \frac{di_3}{dt}$$.

Substituindo $$i_1$$ e $$i_2$$ na equação da fonte:

$$
E = R_1\left(C\frac{dv}{dt} + i_3\right) + v.
$$

Claro! Vamos refazer a dedução usando a carga $$q$$ no capacitor em vez da tensão $$v$$. Lembre que:

$$
v = \frac{q}{C}, \quad i_2 = \frac{dq}{dt}.
$$

As variáveis de estado são: corrente no indutor $$i_3$$ e carga no capacitor $$q$$.  
O circuito: fonte $$E$$, resistor $$R_1$$ em série com um paralelo formado pelo capacitor $$C$$ e o ramo $$R_2$$-L.  
Correntes: $$i_1$$ (em $$R_1$$), $$i_2$$ (no capacitor), $$i_3$$ (no indutor e em $$R_2$$), com $$i_1 = i_2 + i_3$$.

---

**1. Equação do ramo $$R_2$$-L** (lei das malhas nesse ramo):

$$
v = R_2 i_3 + L \frac{di_3}{dt}.
$$

Substituindo $$v = q/C$$:

$$
\frac{q}{C} = R_2 i_3 + L \frac{di_3}{dt}
\quad\Rightarrow\quad
L \frac{di_3}{dt} = \frac{q}{C} - R_2 i_3
\quad\Rightarrow\quad
\frac{di_3}{dt} = -\frac{R_2}{L} i_3 + \frac{1}{LC}\, q.
$$

---

**2. Equação da malha principal** (fonte, $$R_1$$ e o paralelo):

$$
E = R_1 i_1 + v = R_1 (i_2 + i_3) + \frac{q}{C}.
$$

Mas $$i_2 = \dfrac{dq}{dt}$$. Logo:

$$
E = R_1 \left( \frac{dq}{dt} + i_3 \right) + \frac{q}{C}.
$$

Isolando $$\dfrac{dq}{dt}$$:

$$
R_1 \frac{dq}{dt} = E - R_1 i_3 - \frac{q}{C}
\quad\Rightarrow\quad
\frac{dq}{dt} = -\frac{1}{R_1 C}\, q - i_3 + \frac{E}{R_1}.
$$

<p>
**Sistema de duas equações diferenciais de primeira ordem** (com entrada E):
<p>
$$
\boxed{
\begin{aligned}
\frac{di_3}{dt} &= -\frac{R_2}{L}\, i_3 + \frac{1}{LC}\, q \\[6pt]
\frac{dq}{dt} &= -\, i_3 - \frac{1}{R_1 C}\, q + \frac{E}{R_1}
\end{aligned}
}
$$

<p>
Na forma matricial (vetor de estado) 
<p>
$$
\mathbf{x} = \begin{bmatrix} i_3 \\ q \end{bmatrix}
$$
<p>
$$
\frac{d}{dt}\begin{bmatrix} i_3 \\ q \end{bmatrix} =
\begin{bmatrix}
-\dfrac{R_2}{L} & \dfrac{1}{LC} \\[6pt]
-1 & -\dfrac{1}{R_1 C}
\end{bmatrix}
\begin{bmatrix} i_3 \\ q \end{bmatrix}
+
\begin{bmatrix} 0 \\ \dfrac{E}{R_1} \end{bmatrix}.
$$
<p>
Caso a fonte seja nula ($$E=0$$), o sistema homogêneo tem a matriz acima, cujos autovalores determinam a estabilidade.
<p>
As matrizes de estado do sistema elétrico, utilizando como variáveis de estado a corrente no indutor $$i_3$$ e a carga q no capacitor, e considerando a tensão da fonte E como entrada u, são:
<p>
$$
\mathbf{x} = \begin{bmatrix} i_3 \\ q \end{bmatrix}, \quad u = E
$$
<p>
$$\dot{\mathbf{x}} = A\,\mathbf{x} + B\,u
$$
<p>
$$
A = \begin{bmatrix}
-\dfrac{R_2}{L} & \dfrac{1}{LC} \\[6pt]
-1 & -\dfrac{1}{R_1 C}
\end{bmatrix}, \qquad
B = \begin{bmatrix} 0 \\[4pt] \dfrac{1}{R_1} \end{bmatrix}
$$
<p>
Se for necessário definir uma saída (por exemplo, a tensão no capacitor $$v = q/C$$ ou a corrente $$i_1$$, podemos incluir as matrizes C e D. Por exemplo, para a saída $$y = v$$ (tensão no capacitor):
<p>
$$
y = \begin{bmatrix} 0 & \dfrac{1}{C} \end{bmatrix} \mathbf{x} + 0\cdot u
\quad\Rightarrow\quad
C = \begin{bmatrix} 0 & \dfrac{1}{C} \end{bmatrix},\quad D = 0.
$$
<p>
Ou, se a saída for o próprio vetor de estados:
<p>
$$
C = I_2 \quad (\text{matriz identidade } 2\times 2),\quad D = \begin{bmatrix} 0 \\ 0 \end{bmatrix}.
$$




