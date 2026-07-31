<h1>Estabilidade - Funções de Lyapunov - 04</h1>

(c) Usando funções de Lyapunov, investigar a estabilidade dos seguintes sistemas:

```math
\frac{dx}{dt} = \begin{bmatrix} 1 & -4 \\ 4 & -7 \end{bmatrix} x
```
---

## Traço e determinante

$$T=\text{traço}(A)=1+(-7)=-6$$

$$D=\det(A)=(1)(-7)-(-4)(4)=-7+16=9$$

## Aplicando a tabela de classificação

$D=9>0$ — então autovalores têm o **mesmo sinal** (produto positivo)

Verificando o discriminante $T^2-4D$:
$$T^2-4D = (-6)^2-4(9)=36-36=0$$

**Caso especial: $T^2-4D=0$** → autovalores reais e **iguais** (raiz dupla)

$$\lambda = \frac{T}{2}=\frac{-6}{2}=-3 \quad \text{(autovalor duplo)}$$

Como $T<0$ (e $D>0$), ambos autovalores são **negativos** → **nó estável** ✓ (nesse caso especial, com autovalores repetidos, é chamado de **nó estável degenerado** ou **nó impróprio**, dependendo de a matriz ser ou não diagonalizável)

## Conclusão

$$T=-6<0, \quad D=9>0, \quad T^2-4D=0 \;\Rightarrow\; \textbf{nó estável}$$

Confirma exatamente o que o gabarito diz: "assintoticamente estável (nó estável)" ✓.

---

Esse foi um caso particular interessante: quando $T^2-4D=0$ exatamente, caímos no limite entre nó (autovalores reais distintos) e foco (autovalores complexos) — autovalores reais e **repetidos**. Vale adicionar essa linha na sua tabela de referência:

| Condição adicional | Classificação |
|---|---|
| $D>0$, $T^2-4D=0$, $T<0$ | Nó estável (degenerado/impróprio) |
| $D>0$, $T^2-4D=0$, $T>0$ | Nó instável (degenerado/impróprio) |
