<h1>Matriz exponencial</h1>

Determine $e^(At)$ para as matrizes A representadas a seguir:

(a)
```math
\begin{bmatrix}2&1&0\\0&2&1\\ 0&0&2 \end{bmatrix}
```

(b)
```math
\begin{bmatrix} 2&0&0\\ 0&2&1\\  0&0&2 \end{bmatrix}
```

(c)
```math
\begin{bmatrix} -1&1&0\\ 0&2&1\\  0&0&2 \end{bmatrix}
```

(d)
```math
\begin{bmatrix} 0&0&0\\ 0&0&0\\  0&0&0 \end{bmatrix}
```


## (a) Bloco de Jordan único (autovalor 2)

$$A = 2I + N, \quad N = \begin{bmatrix}0&1&0\\0&0&1\\0&0&0\end{bmatrix}$$

Como $N^2 = \begin{bmatrix}0&0&1\\0&0&0\\0&0&0\end{bmatrix}$ e $N^3 = 0$:

$$e^{Nt} = I + Nt + \frac{N^2t^2}{2}$$

Logo:

$$e^{At} = e^{2t}\begin{bmatrix}1 & t & t^2/2\\0&1&t\\0&0&1\end{bmatrix}$$

## (b) Matriz em blocos

$$A = \begin{bmatrix}2&0&0\\0&2&1\\0&0&2\end{bmatrix}$$

Aqui há um bloco $1\times1$ (o "2" isolado) e um bloco $2\times2$ do tipo Jordan. Como a matriz é bloco-diagonal, calculamos $e^{At}$ em cada bloco separadamente:

- Bloco $[2]$: $e^{2t}$
- Bloco $\begin{bmatrix}2&1\\0&2\end{bmatrix} = 2I+N$: $e^{2t}\begin{bmatrix}1&t\\0&1\end{bmatrix}$

$$e^{At} = \begin{bmatrix}e^{2t} & 0 & 0\\0 & e^{2t} & te^{2t}\\0&0&e^{2t}\end{bmatrix}$$

## (c) Autovalores distintos (-1 e 2 duplo) — precisa de Laplace

$$A = \begin{bmatrix}-1&1&0\\0&2&1\\0&0&2\end{bmatrix}$$

Aqui a diagonal **não** é constante, então não dá para escrever $A=\lambda I+N$ com $N$ comutando. O jeito mais limpo é usar $e^{At} = \mathcal{L}^{-1}\{(sI-A)^{-1}\}$.

$$sI - A = \begin{bmatrix}s+1&-1&0\\0&s-2&-1\\0&0&s-2\end{bmatrix}$$

Resolvendo por substituição regressiva (matriz triangular superior) coluna a coluna, obtemos:

$$(sI-A)^{-1} = \begin{bmatrix} \dfrac{1}{s+1} & \dfrac{1}{(s+1)(s-2)} & \dfrac{1}{(s+1)(s-2)^2} \\[2mm] 0 & \dfrac{1}{s-2} & \dfrac{1}{(s-2)^2} \\[2mm] 0 & 0 & \dfrac{1}{s-2}\end{bmatrix}$$

Usando frações parciais e transformando termo a termo:
- $\dfrac{1}{s+1}\to e^{-t}$
- $\dfrac{1}{s-2}\to e^{2t}$
- $\dfrac{1}{(s-2)^2}\to te^{2t}$
- $\dfrac{1}{(s+1)(s-2)} = \dfrac{1/3}{s-2}-\dfrac{1/3}{s+1} \to \dfrac{e^{2t}-e^{-t}}{3}$
- $\dfrac{1}{(s+1)(s-2)^2} = \dfrac{1/9}{s+1}-\dfrac{1/9}{s-2}+\dfrac{1/3}{(s-2)^2} \to \dfrac{1}{9}e^{-t}-\dfrac{1}{9}e^{2t}+\dfrac{1}{3}te^{2t}$

$$e^{At} = \begin{bmatrix} e^{-t} & \dfrac{e^{2t}-e^{-t}}{3} & \dfrac{1}{9}e^{-t}-\dfrac{1}{9}e^{2t}+\dfrac{1}{3}te^{2t} \\[2mm] 0 & e^{2t} & te^{2t} \\[2mm] 0&0&e^{2t}\end{bmatrix}$$

## (d) Matriz nula

$$A = 0 \implies e^{At} = I = \begin{bmatrix}1&0&0\\0&1&0\\0&0&1\end{bmatrix}$$

(Direto da série: $e^{At} = I + At + \dots$, e como $A=0$, todos os termos além de $I$ somem.)

