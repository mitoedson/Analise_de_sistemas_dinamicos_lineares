# Fundamentos de Sistemas Dinâmicos Lineares Multivariáveis

# 1. O que é um Sistema?
Um **sistema** é definido como uma combinação de componentes, ou um conjunto de partes, que compõem um todo e agem em conjunto para atingir um objetivo específico. Na engenharia e matemática, os sistemas são classificados em diversas categorias, sendo as principais:
<p align="center">
<img width="510" height="299" alt="image" src="https://github.com/user-attachments/assets/54257aa8-c76f-4e63-a578-5f2ffb8494af" />
<p>
<ul>
<li><b>Estáticos vs. Dinâmicos:</b> Sistemas estáticos têm saídas que dependem apenas da entrada atual, enquanto sistemas dinâmicos possuem "memória", ou seja, seu comportamento atual e futuro depende de ocorrências passadas.
<li><b>Lineares vs. Não lineares:</b> Sistemas lineares obedecem ao princípio da superposição.
<li><b>Monovariáveis vs. Multivariáveis:</b> Sistemas monovariáveis (SISO) possuem uma única entrada e saída, enquanto sistemas multivariáveis (MIMO) lidam com múltiplas entradas e saídas simultaneamente.
</ul>

## 2. Sistemas Dinâmicos Lineares Multivariáveis
Sistemas multivariáveis são complexos pois as variáveis internas podem estar interconectadas. Para analisá-los, a abordagem mais eficiente é a **representação no espaço de estados**, que organiza as equações diferenciais em um conjunto de equações de primeira ordem na forma vetorial-matricial.

### 2.1 A Estrutura do Espaço de Estados
A representação padrão de um sistema dinâmico linear invariante no tempo é composta por duas equações fundamentais:

1.  **Equação de Estado:** $\dot{x}(t) = Ax(t) + Bu(t)$
2.  **Equação de Saída:** $y(t) = Cx(t) + Du(t)$

Onde:
*   **$x(t)$** é o **vetor de estado** (contém as variáveis de "memória" do sistema, como posição e velocidade).
*   **$u(t)$** é o **vetor de entrada** (sinais de controle ou perturbações).
*   **$y(t)$** é o **vetor de saída** (variáveis medidas de interesse).
*   **$A$** é a **matriz de estados** ($n \times n$), que define a dinâmica interna.
*   **$B$** é a **matriz de entrada**, que relaciona as entradas aos estados.
*   **$C$** é a **matriz de saída** e **$D$** é a matriz de transmissão direta.

## 3. Modelagem Matemática (Exemplo Prático)
Considere um sistema de **dois carrinhos interligados** por molas e amortecedores. Este é um exemplo clássico de sistema multivariável, pois o movimento do carrinho 1 afeta o carrinho 2 e vice-versa.
<p align="center">
<img width="465" height="147" alt="image" src="https://github.com/user-attachments/assets/63acb173-f50c-4285-a4af-f6338e34b821" />
<p>
Ao aplicar a Segunda Lei de Newton ($F = ma$) para cada massa, obtemos equações diferenciais de segunda ordem. Para transformar esse sistema em espaço de estados, definimos as posições ($w_1, w_2$) e as velocidades ($\dot{w}_1, \dot{w}_2$) como as quatro variáveis de estado ($x_1$ a $x_4$). O resultado final é uma matriz $A$ de dimensão $4 \times 4$ que descreve como todas essas variáveis interagem ao longo do tempo.

## 4. Análise de Estabilidade
A estabilidade é a característica mais importante de um sistema dinâmico. Em sistemas lineares multivariáveis, ela é determinada pelos <a href="/teoria/autovaloreseautovetores.md">autovalores</a> da matriz $A$.

*   **Método Indireto de Lyapunov:** Um sistema é **assintoticamente estável** se as partes reais de todos os <a href="/teoria/autovaloreseautovetores.md">autovalores</a> da matriz $A$ forem **negativas**.
*   Se pelo menos um autovalor tiver parte real positiva, o sistema é **instável**.
*   Os autovalores são as raízes da **equação característica**, obtida por $\det(A - \lambda I) = 0$.

## 5. Propriedades Estruturais
Para que um sistema multivariável seja controlável e operável na prática, ele deve satisfazer dois conceitos introduzidos por Kalman:

*   **Controlabilidade:** Capacidade de transferir o sistema de qualquer estado inicial para qualquer estado final através das entradas em tempo finito.
*   **Observabilidade:** Capacidade de determinar o estado inicial do sistema apenas observando as saídas e entradas durante um intervalo de tempo.

### Resumo de Fixação
Um sistema dinâmico linear multivariável é melhor compreendido através de **matrizes**. A matriz de estados **$A$** governa a "saúde" (estabilidade) e a resposta natural, enquanto as matrizes **$B, C, D$** ditam como o mundo externo interage com o sistema.

<p>
<a href="/exercicios/modelagem01.md">Ver exercício 01</a><br>
<a href="/exercicios/modelagem02.md">Ver exercício 02</a>  
</p>
