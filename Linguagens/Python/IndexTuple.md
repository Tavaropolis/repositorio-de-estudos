<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [count()](./IndexTuple.md)

# index()

Funciona como o **index()** das [listas](./List.md), ela retorna o índice do valor passado como argumento.

Caso tenha mais de um mesmo valor na tupla, será retornado o índice do primeiro localizado.

Se o valor passado não existir na lista, será retornado um erro.

```python
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)

x = thistuple.index(8)

print(x)
```