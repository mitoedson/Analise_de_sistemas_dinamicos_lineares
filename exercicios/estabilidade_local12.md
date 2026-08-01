<h1>Estabilidade Local - 12</h1>

Considere o sistema de segunda ordem descrito por:

```math
\dot x = ax - bxy
```
```math
\dot y = cxy - dy
```

na qual, a, b, c e d são constantes reais positivas. Determine os pontos de equilíbrio. Para cada um desses pontos de equilíbrio determine a estabilidade e o tipo de ponto
de equilíbrio (sela, foco, nó, centro).

---

**1. Encontrar os pontos críticos**

Resolver $\dot x=0$ e $\dot y=0$ simultaneamente. Técnicas comuns:

```math
\dot x = 0 \Rightarrow ax - bxy = 0 \Rightarrow ax = bxy \Rightarrow y = \frac{ax}{bx} 
```
```math
\dot y = 0 \Rightarrow cxy - dy = 0 \Rightarrow cxy = dy
```



- Isolar uma variável e substituir na outra equação
- Fatorar em casos (quando as equações já vêm como produtos, como $x(1-x-y)=0$)
- Combinar as soluções possíveis, testando compatibilidade entre os casos







**2. Montar a matriz Jacobiana genérica**

```math
J(x,y)=\begin{pmatrix}\dfrac{\partial f}{\partial x} & \dfrac{\partial f}{\partial y}\\[4pt]\dfrac{\partial g}{\partial x} & \dfrac{\partial g}{\partial y}\end{pmatrix}
```
Essa matriz representa a **aproximação linear** (expansão de Taylor de 1ª ordem) do sistema em torno de um ponto qualquer.

**3. Avaliar o Jacobiano em cada ponto crítico**

Substituindo as coordenadas de cada ponto na matriz genérica, obtém-se uma matriz numérica constante para cada ponto — essa matriz descreve o comportamento **linearizado**, válido apenas **naquela vizinhança específica**.

**4. Calcular traço ($T$) e determinante ($D$)**

$$T=\text{soma da diagonal}, \qquad D=\det(J)$$

**5. Classificar usando a tabela T-D**

| Condição | Classificação |
|---|---|
| $D<0$ | Sela (sempre instável) |
| $D>0$, $T^2-4D>0$, $T>0$ | Nó instável |
| $D>0$, $T^2-4D>0$, $T<0$ | Nó estável |
| $D>0$, $T^2-4D<0$, $T>0$ | Foco instável |
| $D>0$, $T^2-4D<0$, $T<0$ | Foco estável |
| $D>0$, $T=0$ | Centro (marginalmente estável) |
| $D>0$, $T^2-4D=0$ | Nó degenerado (próprio ou impróprio) |
