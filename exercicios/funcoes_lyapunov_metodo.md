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

```math
\dot V = \dot{\mathbf x}^T P\mathbf x + \mathbf x^T P\dot{\mathbf x} = \mathbf x^T(A^TP+PA)\mathbf x
```

A ideia prática mais comum: **escolher $Q$ positiva definida** (geralmente $Q=I$, a identidade, por simplicidade) e resolver a **equação de Lyapunov**:

```math
A^TP+PA = -Q
```


Se conseguirmos encontrar $P$ **positiva definida** que resolve essa equação, então $V=\mathbf x^TP\mathbf x$ é válida ($V>0$) e $\dot V=-\mathbf x^TQ\mathbf x<0$ → sistema **assintoticamente estável**.
