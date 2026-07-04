<h1>Linearização de sistemas dinâmicos não-lineares</h1>

Foco no estudo e cálculo da **matriz exponencial** ($e^{\mathbf{A}t}$), ferramenta central para a resolução de sistemas dinâmicos lineares multivariáveis descritos por equações de estado.

### 1. Definição e Propriedades Fundamentais
O material parte da analogia com equações diferenciais escalares ($\dot{x} = ax$) para definir a solução de sistemas matriciais homogêneos ($\dot{\mathbf{x}} = \mathbf{Ax}$) como $\mathbf{x}(t) = e^{\mathbf{A}t}\mathbf{x}(0)$. A matriz exponencial é definida formalmente por uma **série de potências de Taylor**:
$$e^{\mathbf{A}t} = \mathbf{I} + \mathbf{A}t + \frac{\mathbf{A}^2t^2}{2!} + \dots = \sum_{k=0}^{\infty} \frac{\mathbf{A}^kt^k}{k!}$$.

Entre as propriedades destacadas, encontram-se:
*   **Convergência:** A série converge de forma absoluta para todos os valores finitos de $t$.
*   **Derivada:** $\frac{d}{dt}e^{\mathbf{A}t} = \mathbf{A}e^{\mathbf{A}t} = e^{\mathbf{A}t}\mathbf{A}$.
*   **Inversibilidade:** A matriz exponencial é sempre não singular, e sua inversa é dada por $(e^{\mathbf{A}t})^{-1} = e^{-\mathbf{A}t}$.
*   **Aditividade:** $e^{\mathbf{A}(t+s)} = e^{\mathbf{A}t}e^{\mathbf{A}s}$.

### 2. Matriz de Transição de Estados ($\Phi(t)$)
Para sistemas lineares invariantes no tempo, a matriz exponencial é identificada como a **matriz de transição de estados**, denotada por $\Phi(t)$. Ela é a solução única para a equação $\dot{\Phi}(t) = \mathbf{A}\Phi(t)$ com a condição inicial $\Phi(0) = \mathbf{I}$, servindo para "transportar" o estado inicial para qualquer instante futuro.

### 3. Resolução de Equações de Estado
O documento detalha como a matriz exponencial resolve diferentes tipos de problemas:
*   **Sistemas Homogêneos:** $\mathbf{x}(t) = e^{\mathbf{A}(t-t_0)}\mathbf{x}(t_0)$.
*   **Sistemas Não Homogêneos ($\dot{\mathbf{x}} = \mathbf{Ax} + \mathbf{Bu}$):** A solução completa é obtida pela **integral de convolução**, somando a resposta natural (condição inicial) à resposta forçada (entrada externa):
    $$\mathbf{x}(t) = e^{\mathbf{A}(t-t_0)}\mathbf{x}(t_0) + \int_{t_0}^{t} e^{\mathbf{A}(t-\tau)}\mathbf{Bu}(\tau)d\tau$$

### 4. Cálculo via Teorema de Cayley-Hamilton
Como a série infinita não é prática, o material explica o uso do **Teorema de Cayley-Hamilton**, que permite expressar $e^{\mathbf{A}t}$ como um **polinômio finito em $t$** de grau $n-1$ (onde $n$ é a ordem da matriz):
$$e^{\mathbf{A}t} = \alpha_{n-1}\mathbf{A}^{n-1}t^{n-1} + \dots + \alpha_1\mathbf{A}t + \alpha_0\mathbf{I}$$
Os coeficientes $\alpha_i$ são determinados substituindo os autovalores de $\mathbf{A}t$ na equação característica correspondente.

### 5. Exemplos e Exercícios Práticos
Exemplos de cálculo para matrizes $2 \times 2$ e $3 \times 3$, cobrindo três cenários de autovalores:
1.  **Reais e Distintos:** Exponenciais simples.
2.  **Complexos:** Resultam em termos trigonométricos (seno e cosseno).
3.  **Múltiplos (Repetidos):** Incluem termos como $te^{\lambda t}$.
