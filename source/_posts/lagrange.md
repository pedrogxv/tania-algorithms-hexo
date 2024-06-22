---
title: Lagrange - Aula 11/06/22024
---

# Objetivo

Desenvolver código para solucionar o valor interpolado via fórmula de lagrande.

## Explicações

O código em Python implementa a função de interpolação de Lagrange, que é usada no cálculo numérico para estimar valores intermediários entre pontos conhecidos.

A função lagrange recebe dois argumentos: x, que é o valor para o qual queremos estimar o resultado, e pontos, que é uma lista de pontos no formato (x, y). A função retorna o valor interpolado para o ponto x.

A implementação utiliza o método de Lagrange, que envolve a construção de polinômios de Lagrange para cada ponto conhecido e, em seguida, somando esses polinômios ponderados. O resultado final é o valor interpolado desejado.

A variável result é inicializada como zero e será usada para armazenar o resultado final da interpolação. A variável n é definida como o número de pontos conhecidos.

Em seguida, há um loop for que itera sobre cada ponto conhecido. Dentro desse loop, a variável term é inicializada com o valor y do ponto atual.

Em seguida, há um segundo loop for que itera sobre todos os pontos conhecidos novamente. Dentro desse loop, é verificado se o índice i é diferente do índice j. Se forem diferentes, o termo é multiplicado por (x - points[j][0]) / (points[i][0] - points[j][0]). Essa é a fórmula do polinômio de Lagrange para cada ponto.

Por fim, o termo é adicionado ao resultado final result.

Após a definição da função lagrange, há a criação de uma lista de pontos pontos e a definição de um valor x para o qual queremos estimar o resultado interpolado.

Em seguida, a função lagrange é chamada com os argumentos x e pontos, e o resultado é armazenado na variável result.

Por fim, o resultado é impresso na tela usando a função print.

Esse código pode ser usado em uma aula de cálculo numérico para demonstrar o conceito de interpolação de Lagrange e como implementá-lo em Python.

## Código Python

```python

def lagrange(x, points):
    result = 0
    n = len(points)

    for i in range(n):
        term = points[i][1]
        for j in range(n):
            if i != j:
                term *= (x - points[j][0]) / (points[i][0] - points[j][0])
        result += term

    return result

pontos = [(1, 2), (3, 4), (5, 6)]
x = 2

result = lagrange(x, pontos)

print(f"O valor interpolado para x = {x} é {result}.")

```
