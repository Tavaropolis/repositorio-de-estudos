<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [lambda](./Lambda.md)

# lambda

As **funções lambda** são funções anônimas, ou seja, funções sem nome, definidas em uma única linha usando a palavra-chave `lambda`. Elas são frequentemente usadas para expressões simples que precisam ser passadas como argumento para funções como [`map()`](./Map.md),[`filter()`](./Filter.md), [`sorted()`](./Sorted.md) e [`reduce()`](./Reduce.md).

A definição do lambda segue a seguinte ideia: 

```python
lambda argumentos: expressão
```

Segue a comparação entre uma função simples e uma `lambda`:

```python
# Função tradicional
def quadrado(x):
    return x ** 2

# Função lambda equivalente
quadrado_lambda = lambda x: x ** 2

print(quadrado(5))         # Saída: 25
print(quadrado_lambda(5))  # Saída: 25
```

## Usando `lambda` em um map()
```python
numeros = [1, 2, 3, 4, 5]
quadrados = list(map(lambda x: x ** 2, numeros))
print(quadrados)  # Saída: [1, 4, 9, 16, 25]
```

## Usando `lambda` em um filter()
```python
numeros = [1, 2, 3, 4, 5, 6]
pares = list(filter(lambda x: x % 2 == 0, numeros))
print(pares)  # Saída: [2, 4, 6]
```

## Usando `lambda` em sorted()
```python
nomes = ["Ana", "Carlos", "Beatriz", "Daniel"]
ordenado = sorted(nomes, key=lambda nome: len(nome))
print(ordenado)  # Saída: ['Ana', 'Carlos', 'Daniel', 'Beatriz']
```