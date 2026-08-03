<h1>Funções de Lyapunov - Método Sistemático</h1>

Para $\dot{\mathbf x}=A\mathbf x$, escolhemos a candidata quadrática:

```math
V(\mathbf x) = \mathbf x^T P \mathbf x
```
onde $P$ é uma matriz simétrica a determinar. 

Repare que se expandirmos, obtemos, para 2 variáveis:

```math
V(x_1,x_2) = p_{11} x_1^2 + 2 p_{12} x_1 x_2 + p_{22} x_2^2
```


Calculando $\dot V$:

Como $$V(x) = x^TPx$$, e $$\dot V = \frac{d}{dt}(x^TPx) = \dot x^T Px + x^TP\dot x \quad\text{(regra da cadeia, regra do produto)}$$

e $$\dot x = Ax$$, $$\dot V = (Ax)^T Px + x^TP(Ax) \Rightarrow V = x^TA^T Px + x^TP(Ax) = x^T(A^TP+PA)x$$ 

Portanto,
```math
\dot V = \dot{\mathbf x}^T P\mathbf x + \mathbf x^T P\dot{\mathbf x} = \mathbf x^T(A^TP+PA)\mathbf x
```


A ideia prática mais comum: **escolher $Q$ positiva definida** (geralmente $Q=I$, a identidade, por simplicidade) e resolver a **equação de Lyapunov**:

```math
A^TP+PA = -Q
```

Como $$A^TP + PA = −I$$, segue que:
```math
\dot V = x^T(A^TP+PA)x = x^T(-I)x = -\begin{bmatrix} x_1 & x_2 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} \Rightarrow \dot V = -(x_1^2+x_2^2) < 0
```


Se conseguirmos encontrar $P$ **positiva definida** que resolve essa equação, então $V=\mathbf x^TP\mathbf x$ é válida ($V>0$) e $\dot V=-\mathbf x^TQ\mathbf x<0$ → sistema **assintoticamente estável**.

## Onde a candidata $V=\mathbf x^TP\mathbf x$ é usada especificamente:

$$\boxed{V=\mathbf x^TP\mathbf x \text{ é a candidata PADRÃO para SISTEMAS LINEARES }}$$

Essa forma **quadrática matricial** é a escolha natural quando o sistema é $\dot{\mathbf x}=A\mathbf x$ (linear), porque ela **generaliza perfeitamente** a ideia de "soma de quadrados" para múltiplas dimensões, permitindo inclusive **pesos diferentes e termos cruzados** entre as variáveis — tudo capturado pelos coeficientes $p_{11}, p_{12}, p_{22}$ (no caso $2\times2$) dentro da matriz $P$.

#### Por que essa forma é tão poderosa para sistemas lineares

Expandindo $V=\mathbf x^TP\mathbf x$ para 2 variáveis:
$$V(x_1,x_2)=p_{11}x_1^2+2p_{12}x_1x_2+p_{22}x_2^2$$

Repare: essa é a forma quadrática **mais geral possível** com 2 variáveis — inclui automaticamente o termo cruzado ($x_1x_2$), o que dá **flexibilidade total** para "ajustar" a candidata através dos coeficientes $p_{ij}$, sem precisar "adivinhar" a estrutura manualmente.

#### Comparando com as candidatas usadas nas questões 3, 5, 6 (sistemas não lineares)

Nessas questões, **não** usamos essa forma matricial genérica — usamos candidatas **mais simples e específicas**, como:

$$V=x^2+y^2, \quad V=x^2+2y^2, \quad V=\frac12x_2^2+\frac18x_1^8, \quad V=\frac12mL^2x_2^2+mgL(1-\cos x_1)$$

#### Por que a diferença — a razão estrutural

$$\boxed{\text{Para sistemas LINEARES: } V=\mathbf x^TP\mathbf x \text{ (forma quadrática GERAL) funciona SEMPRE, com um método SISTEMÁTICO (equação de Lyapunov) para encontrar } P}$$

$$\boxed{\text{Para sistemas NÃO LINEARES: não existe uma forma "geral" garantida — a candidata precisa ser ADAPTADA à estrutura específica do sistema (expoentes, termos trigonométricos, interpretação física)}}$$

#### Uma observação interessante — poderíamos usar $V=\mathbf x^TP\mathbf x$ em sistemas não lineares também?

Tecnicamente, **sim** — é só uma **candidata quadrática genérica**, que poderia ser tentada em qualquer sistema. Mas repare que, nos itens da questão 5, quando ajustamos pesos (como $V=x^2+2y^2$ no item b), estávamos **essencialmente** escolhendo:

```math
P=\begin{pmatrix}1&0\\0&2\end{pmatrix}
```

Ou seja, **implicitamente** já estávamos usando um caso particular (diagonal) de $V=\mathbf x^TP\mathbf x$! A diferença é que, para sistemas não lineares, **não existe uma equação sistemática** (como a de Lyapunov linear) que nos diga automaticamente quais valores de $P$ escolher — precisamos **descobrir por tentativa**, guiados pela estrutura do sistema.

#### Resumindo a conexão completa

$$\boxed{\text{A forma } V=\mathbf x^TP\mathbf x \text{ é, na verdade, a "candidata mãe" — usada explicitamente na questão 4, e usada IMPLICITAMENTE (via ajuste de pesos) em várias candidatas da questão 5}}$$



