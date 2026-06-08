<h1>Modelagem matemática</h1>

<img width="514" height="483" alt="image" src="https://github.com/user-attachments/assets/6e31975f-384f-4fd6-9c5b-ef8772dbf01b" />

<p>
 # Sistema mecânico com duas massas, duas molas e um amortecedor

## Descrição do sistema

- Mola $k_1$ fixa no teto, ligada à massa $m_1$;
- Mola $k_2$ fixa no teto, ligada à massa $m_2$;
- Amortecedor $b_1$ conectando $m_1$ e $m_2$;
- Forças externas $u_1(t)$ (para baixo em $m_1$) e $u_2(t)$ (para baixo em $m_2$);
- Deslocamentos $y_1(t)$ e $y_2(t)$ medidos a partir do equilíbrio estático (para baixo).

---

## (a) Equações diferenciais

Aplicando a segunda lei de Newton:
<p>
<b>Massa m_1:</b>
<p>$$ m_1 \ddot{y}_1 = -k_1 y_1 - b_1(\dot{y}_1 - \dot{y}_2) + u_1(t) $$
<p><b>Massa m_2:</b> 
<p align=left>$$ m_2 \ddot{y}_2 = -k_2 y_2 + b_1(\dot{y}_1 - \dot{y}_2) + u_2(t) $$
<p>
Reescrevendo na forma padrão:
<p>
$$\begin{aligned}
m_1 \ddot{y}_1 + b_1 \dot{y}_1 - b_1 \dot{y}_2 + k_1 y_1 &= u_1(t) \\[4pt]
m_2 \ddot{y}_2 - b_1 \dot{y}_1 + b_1 \dot{y}_2 + k_2 y_2 &= u_2(t)
\end{aligned} $$
<p><br>
<b>(b) Variáveis de estado</b>
<p>
Definindo $x_1 = y_1$, $x_2 = \dot{y}_1$, $x_3 = y_2$, $x_4 = \dot{y}_2$:
<p>
$$
\begin{aligned}
\dot{x}_1 &= x_2 \\
\dot{x}_2 &= \frac{1}{m_1}\bigl( u_1(t) - k_1 x_1 - b_1 x_2 + b_1 x_4 \bigr) \\
\dot{x}_3 &= x_4 \\
\dot{x}_4 &= \frac{1}{m_2}\bigl( u_2(t) + b_1 x_2 - b_1 x_4 - k_2 x_3 \bigr)
\end{aligned}
$$
<p>
<b>(c) Forma vetorial–matricial</b>
<p>
$$
\dot{\mathbf{X}} = A\,\mathbf{X} + B\,\mathbf{u},\qquad 
\mathbf{y} = C\,\mathbf{X}
$$

com
<p>
$$
\mathbf{X} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix},\quad 
\mathbf{u} = \begin{bmatrix} u_1(t) \\ u_2(t) \end{bmatrix},\quad 
\mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \end{bmatrix}
$$
</p>
<p>
$$
A = \begin{bmatrix}
0 & 1 & 0 & 0 \\[4pt]
-\dfrac{k_1}{m_1} & -\dfrac{b_1}{m_1} & 0 & \dfrac{b_1}{m_1} \\[8pt]
0 & 0 & 0 & 1 \\[4pt]
0 & \dfrac{b_1}{m_2} & -\dfrac{k_2}{m_2} & -\dfrac{b_1}{m_2}
\end{bmatrix},\qquad
B = \begin{bmatrix}
0 & 0 \\[4pt]
\dfrac{1}{m_1} & 0 \\[8pt]
0 & 0 \\[4pt]
0 & \dfrac{1}{m_2}
\end{bmatrix},\qquad
C = \begin{bmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0
\end{bmatrix}
$$

---

## (d) Simulação no Octave/Matlab

Parâmetros (valores fornecidos ou adotados):

- $m_1 = 1$, $m_2 = 1$
- $k_1 = 0.5$, $k_2 = 1$ (valor adotado, pois não foi fornecido)
- $b_1 = 0.1$
- $u_1(t) = \sin(t)$, $u_2(t) = \cos(t)$
- Condições iniciais nulas: $y_1(0)=0$, $\dot{y}_1(0)=0$, $y_2(0)=0$, $\dot{y}_2(0)=0$

Código:

```matlab
% Parâmetros
m1 = 1; m2 = 1; k1 = 0.5; k2 = 1; b1 = 0.1;

% Matrizes
A = [0, 1, 0, 0;
     -k1/m1, -b1/m1, 0, b1/m1;
     0, 0, 0, 1;
     0, b1/m2, -k2/m2, -b1/m2];

B = [0, 0;
     1/m1, 0;
     0, 0;
     0, 1/m2];

C = [1, 0, 0, 0;
     0, 0, 1, 0];

% Tempo de simulação
tspan = [0, 20];
x0 = [0; 0; 0; 0];

% Entradas
u1 = @(t) sin(t);
u2 = @(t) cos(t);

% Sistema: dx/dt = A*x + B*[u1; u2]
f = @(t, x) A*x + B*[u1(t); u2(t)];

% Resolução
[t, x] = ode45(f, tspan, x0);

% Saídas
y1 = x(:,1);
y2 = x(:,3);

% Gráficos
figure;
subplot(2,1,1);
plot(t, y1, 'b-', 'LineWidth', 1.5);
xlabel('Tempo (s)'); ylabel('y_1(t)');
title('Deslocamento da massa m_1');
grid on;

subplot(2,1,2);
plot(t, y2, 'r-', 'LineWidth', 1.5);
xlabel('Tempo (s)'); ylabel('y_2(t)');
title('Deslocamento da massa m_2');
grid on;

```
<img width="2212" height="812" alt="image" src="https://github.com/user-attachments/assets/f2f44818-5477-44c0-a781-f56481372877" />



