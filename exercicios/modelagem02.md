<h1>Modelagem matemática 02</h1>

<a href="/teoria/introducao.md">Ver teoria</a>
<p>
<img width="518" height="213" alt="image" src="https://github.com/user-attachments/assets/77d6ca16-9a4f-48b0-8b19-ce865458dfa4" />

### Descrição do sistema

- Duas massas $$m_1$$ e $$m_2$$ sobre uma superfície sem atrito.
- Entre $$m_1$$ e $$m_2$$: uma mola $$k_2$$ e um amortecedor $$b$$ em paralelo.
- A massa $$m_2$$ está ligada a uma parede fixa por uma mola $$k_3$$.
- Força externa $$u$$ atua sobre $$m_2$$ comprimindo $$k_3$$ (sentido positivo: para a direita).
- Saídas: deslocamentos $$y_1$$ (de $$m_1$$) e $$y_2$$ (de $$m_2$$), medidos a partir do equilíbrio.
<p>
<b>(a) Equações diferenciais</b>
<p>
Aplicando a segunda lei de Newton a cada massa (considerando deslocamentos positivos para a direita):
<p>
Massa $$m_1$$:<br>  
Força da mola $$k_2$$: $$k_2 (y_2 - y_1)$$<br>
Força do amortecedor: $$b (\dot{y}_2 - \dot{y}_1)$$<br>  
Sem outras forças.
<p>
$$
m_1 \ddot{y}_1 = k_2 (y_2 - y_1) + b (\dot{y}_2 - \dot{y}_1)
$$
<p>
Massa $$m_2$$:<br>
Força da mola $$k_2$$: $$-k_2 (y_2 - y_1)$$<br>
Força do amortecedor: $$-b (\dot{y}_2 - \dot{y}_1)$$<br>  
Força da mola $$k_3$$: $$-k_3 y_2$$<br>  
Força externa: $$+ u$$
<p>
$$
m_2 \ddot{y}_2 = -k_2 (y_2 - y_1) - b (\dot{y}_2 - \dot{y}_1) - k_3 y_2 + u
$$
<p>
Reescrevendo na forma padrão:
<p>
$$
\begin{aligned}
m_1 \ddot{y}_1 + b \dot{y}_1 - b \dot{y}_2 + k_2 y_1 - k_2 y_2 = 0
\end{aligned}$$
$$\begin{aligned}
m_2 \ddot{y}_2 - b \dot{y}_1 + b \dot{y}_2 - k_2 y_1 + (k_2 + k_3) y_2 = u
\end{aligned}$$
<p>
<b>(b) Variáveis de estado</b>
<p>
Definindo $$x_1 = y_1,\; x_2 = \dot{y}_1,\; x_3 = y_2,\; x_4 = \dot{y}_2$$, obtemos o sistema de primeira ordem:
<p>
$$\begin{aligned}\dot{x}_1 &= x_2 \end{aligned}$$
$$\begin{aligned}\dot{x}_2 &= \frac{1}{m_1}\Bigl( -k_2 x_1 - b x_2 + k_2 x_3 + b x_4 \Bigr) \end{aligned}$$
$$\begin{aligned}\dot{x}_3 &= x_4 \end{aligned}$$
$$\begin{aligned}\dot{x}_4 &= \frac{1}{m_2}\Bigl( k_2 x_1 + b x_2 - (k_2 + k_3) x_3 - b x_4 + u \Bigr)\end{aligned}$$
<p>
<b>(c) Forma vetorial–matricial</b>
<p>
$$
\dot{\mathbf{X}} = A \mathbf{X} + B u,\qquad \mathbf{y} = C \mathbf{X}
$$
<p>
com
<p>
$$
\mathbf{X} = \begin{bmatrix} x_1 \\ x_2 \\ x_3 \\ x_4 \end{bmatrix},\quad
\mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \end{bmatrix}
$$
<p>
$$
A = \begin{bmatrix}
0 & 1 & 0 & 0 \\[4pt]
-\dfrac{k_2}{m_1} & -\dfrac{b}{m_1} & \dfrac{k_2}{m_1} & \dfrac{b}{m_1} \\[8pt]
0 & 0 & 0 & 1 \\[4pt]
\dfrac{k_2}{m_2} & \dfrac{b}{m_2} & -\dfrac{k_2+k_3}{m_2} & -\dfrac{b}{m_2}
\end{bmatrix},\qquad
B = \begin{bmatrix} 0 \\ 0 \\ 0 \\ \dfrac{1}{m_2} \end{bmatrix},\qquad
C = \begin{bmatrix} 1 & 0 & 0 & 0 \\ 0 & 0 & 1 & 0 \end{bmatrix}$$
<p>
<b>Observação</b>
<p>
A entrada $$u$$ atua diretamente apenas sobre a massa $$m_2$$. O acoplamento entre as duas massas é feito pela mola $$k_2$$ e pelo amortecedor $$b$$. Este sistema está na forma <b>malha aberta</b>; para estabilizar as saídas em valores constantes seria necessário um controlador realimentado (ex.: PID).
