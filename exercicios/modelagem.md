<h1>Modelagem matemática 01</h1>

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

<p><br><b>Interpretação dos resultados nos gráficos</b>
<p>
Ao executar a simulação descrita, você obtém dois gráficos: o deslocamento $$y_1(t)$$ da massa $$m_1$$ e o deslocamento $$y_2(t)$$ da massa $$m_2$$ ao longo do tempo (por exemplo, de $$t=0$$ a $$t=20$$ s. Eis como interpretar essas curvas à luz dos dados e da teoria.
<p>
### 1. Regime transitório e permanente

- **Regime transitório (inicial):**  
  Nas primeiras unidades de tempo (tipicamente $$t < 5$$ s), as massas partem do repouso ($$y=0$$, $$\dot{y}=0$$) e começam a responder às forças $$sin(t)$$ e $$cos(t)$$. Durante esse período, as trajetórias mostram uma **oscilação que ainda não atingiu um padrão repetitivo** – há uma "acomodação" inicial devido ao amortecimento $$(b_1 = 0,1)$$. Esse efeito transitório é mais visível se você ampliar a região próxima de $$(t=0)$$.

- **Regime permanente (após ~5–10 s):**  
  Após o transitório, as oscilações tornam‑se **periódicas**, com a mesma frequência fundamental das entradas (frequência angular $$\omega = 1$$ rad/s, pois $$u_1=\sin t$$ e $$u_2=\cos t$$ têm período $$2\pi \approx 6,28$$ s). Nesse regime, as amplitudes e as defasagens relativas ficam constantes.

### 2. Frequências observadas

No regime permanente, você deve ver que **tanto $$y_1(t)$$ quanto $$y_2(t)$$ oscilam com frequência igual a 1 rad/s** (período de ~6,28 s), pois o sistema é linear e está sendo forçado por funções senoidais puras. Se houvesse alguma frequência natural do sistema não amortecido muito próxima de 1 rad/s, poderia ocorrer ressonância (amplitude elevada), mas com $$k_1=0,5$$, $$k_2=1$$, $$m_1=m_2=1$$ e $$b_1$$ pequeno, as frequências naturais são aproximadamente:
<p>
$$
\omega_{n1} \approx \sqrt{\frac{k_1}{m_1}} = \sqrt{0,5} \approx 0,707,\quad
\omega_{n2} \approx \sqrt{\frac{k_2}{m_2}} = \sqrt{1} = 1
$$
<p>
Como a força $$(u_2(t) = cos t)$$ excita justamente na frequência natural de $$m_2$$, pode ocorrer uma **ressonância próxima** nessa massa, resultando em amplitude maior para $$y_2$$ do que para $$y_1$$ (verifique no gráfico).

### 3. Comparação entre $$y_1(t)$$ e $$y_2(t)$$

- **Amplitude de oscilação:**  
  Espera‑se que $$y_2$$ tenha amplitude maior do que $$y_1$$ porque a força $$\cos t$$ está diretamente em $$m_2$$ e sua frequência coincide com $$\sqrt{k_2/m_2}=1$$. Já $$m_1$$ é forçada por $$\sin t$$ numa frequência (1 rad/s) diferente de sua frequência natural ($$\approx 0,707$$), e ainda sofre acoplamento via amortecedor $$b_1$$.

- **Defasagem (atraso) entre $$y_1$$ e $$y_2$$:**  
  O amortecedor $$b_1$$ introduz um **atraso** entre o movimento das duas massas. Em geral, a massa $$m_1$$ responde com certo atraso em relação à força $$u_1$$, e a massa $$m_2$$ responde com atraso em relação a $$u_2$$. Além disso, o acoplamento faz com que $$y_1$$ e $$y_2$$ não estejam nem em fase nem em oposição de fase – você pode observar um **defasamento** constante no regime permanente.

### 4. Efeito do amortecimento ($$b_1 = 0,1$$)

Com um amortecimento pequeno, mas não nulo, o transitório desaparece depois de algumas oscilações e as amplitudes no regime permanente são finitas (não explodem). Se $$b_1$$ fosse maior (ex.: 0,5), o transitório seria mais curto e as amplitudes seriam menores. Se $$b_1$$ fosse zero (sem amortecedor), as respostas seriam puramente oscilatórias sem atenuação do transitório, e poderiam até crescer ilimitadamente se a frequência de excitação coincidisse com uma frequência natural (caso de ressonância pura).

### 5. Informações quantitativas que você pode extrair

- **Valor de pico máximo** (positivo e negativo) de $$y_1$$ e de $$y_2$$ após o transitório. Compare com a amplitude teórica esperada (pode ser obtida por resposta em frequência, mas a simulação já fornece o valor numérico).
- **Período de oscilação** – meça a distância entre dois picos consecutivos no regime permanente; deve dar aproximadamente $$2\pi \approx 6,28$$ s.
- **Atraso entre $$y_1$$ e $$y_2$$** – por exemplo, identifique o instante em que $$y_1$$ atinge um máximo e veja quanto tempo depois $$y_2$$ atinge o máximo (ou vice‑versa). Esse atraso pode ser convertido em ângulo de fase: $$\phi = 2\pi \cdot (\text{atraso}) / T$$.

### 6. Comparação com os cálculos analíticos (opcional)

Se você tivesse calculado a solução analítica do sistema (por exemplo, usando transformada de Laplace ou resposta em frequência), poderia comparar os valores numéricos das amplitudes e fases obtidos na simulação com os valores teóricos. Para um sistema linear, o erro numérico do `ode45` é muito pequeno, então os gráficos devem coincidir com a solução exata dentro da precisão gráfica.

### Exemplo prático (hipotético)

Suponha que após rodar o código você veja:

- $$y_1(t)$$: oscila com amplitude ≈ 0,7, atrasada em relação a $$sin t$$ (entrada).
- $$y_2(t)$$: oscila com amplitude ≈ 1,2, ligeiramente atrasada em relação a $$cos t$$.

**Interpretação:** A massa $$m_2$$ entra em ressonância quase total (pois sua frequência natural é 1 rad/s), por isso sua amplitude é maior. O amortecedor $$b_1 = 0,1$$ limita essa amplitude, caso contrário seria infinita (se $$b_1=0$$ e sem atrito). Já $$m_1$$ oscila com amplitude menor, pois sua frequência natural é diferente e ela é “puxada” pelo amortecedor, que transfere parte da energia de $$m_2$$ para $$m_1$$, mas não o suficiente para igualar as amplitudes.

Essas observações confirmam o comportamento esperado do sistema de duas massas acoplado por um amortecedor.

Caso você tenha os gráficos reais (por exemplo, no Octave), posso ajudá‑lo a interpretar valores específicos (máximos, ângulos de fase). Basta descrever o que você vê ou anexar uma imagem.</p>

