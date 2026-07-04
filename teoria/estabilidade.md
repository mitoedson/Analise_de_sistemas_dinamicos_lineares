<h1>Estabilidade</h1>

### 1. Conceito de Linearização e Sistemas Quase-Lineares
O documento define que um sistema autônomo não linear da forma $x' = f(x)$ pode ser examinado na vizinhança de um ponto crítico (como a origem $x^* = 0$) ao ser reescrito como:
$$x' = Ax + g(x)$$
Nesta estrutura, o termo **$Ax$** representa o **sistema linearizado**, enquanto $g(x)$ contém os termos de ordem superior. O sistema é classificado como **quase-linear** se a magnitude de $g(x)$ diminuir mais rapidamente que a magnitude de $x$ conforme ele se aproxima do ponto crítico ($\|g(x)\|/\|x\| \to 0$ quando $x \to 0$).

### 2. O Método da Matriz Jacobiana
Para realizar a linearização de forma sistemática, utiliza-se a **Expansão em Série de Taylor** das funções do sistema. O documento destaca que a matriz de estados $A$ do sistema linearizado é a **matriz Jacobiana**, composta pelas derivadas parciais das funções do sistema avaliadas no ponto de equilíbrio:
$$A = \left[ \frac{\partial f_i}{\partial x_j} \right]$$

### 3. Análise de Estabilidade (Teorema de Lyapunov)
A fonte estabelece critérios claros para determinar a estabilidade do sistema não linear original a partir dos autovalores ($\lambda$) da matriz Jacobiana $A$:
*   **Assintoticamente Estável:** Ocorre se as partes reais de **todos** os autovalores forem negativas ($\text{Re}\{\lambda_i\} < 0$).
*   **Instável:** Ocorre se **pelo menos um** autovalor tiver a parte real positiva ($\text{Re}\{\lambda_i\} > 0$).

### 4. Estudo de Caso: O Pêndulo
O material utiliza o **pêndulo simples** como exemplo prático para ilustrar a técnica. Ele demonstra como transformar a equação de segunda ordem em variáveis de estado e realiza a linearização em dois pontos distintos:
*   **Na origem $(0, 0)$:** Resulta em um sistema que pode ser estável (dependendo do amortecimento $\gamma$), representando o pêndulo na posição vertical inferior.
*   **No ponto $(\pi, 0)$:** O sistema linearizado apresenta comportamento de instabilidade (ponto de sela), representando o pêndulo equilibrado na vertical superior.
