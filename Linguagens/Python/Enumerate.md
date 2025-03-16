<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [enumerate()](./Enumerate.md)

# enumerate()

A função **enumerate()** é uma função embutida em [Python](./Index.md) que permite iterar sobre uma sequência (como [listas](./List.md), [tuplas](./Tuple.md) ou [strings](./Str.md)) ao mesmo tempo em que acompanha o índice de cada elemento.

Segue um exemplo de como aplicar **enumerate()**:

```python
frutas = ['maçã', 'banana', 'cereja']

for indice, fruta in enumerate(frutas):
    print(f"{indice}: {fruta}")

"""Saída: 
0: maçã
1: banana
2: cereja
"""
```

Podemos passar um segundo parametro chamado `start`, que define o número que irá ser o primeiro índice: 
```python
frutas = ['maçã', 'banana', 'cereja']

for indice, fruta in enumerate(frutas, start=10):
    print(f"{indice}: {fruta}")

"""Saída: 
10: maçã
11: banana
12: cereja
"""
```

O retorno do **enumerate()** é um objeto do tipo `enumerate`. Ele pode ser tranformado em uma lista de tuplas:

```
frutas = ['maçã', 'banana', 'cereja']

lista_enumerada = list(enumerate(frutas))
print(lista_enumerada)
```