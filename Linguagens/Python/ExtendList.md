<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [extend()](./ExtendList.md)

# extend()

**extend()** é uma função que faz o mesmo que a [concatenação de listas](./ConcatList.md), ou seja junta duas listas em uma.

Lembrando que ele é um método de lista, ou seja é necessário ter uma lista instanciada para poder usar.

```python
thislist = ["apple", "banana", "cherry"]
tropical = ["mango", "pineapple", "papaya"]

thislist.extend(tropical)

print(thislist)

"""retorno no terminal
['apple', 'banana', 'cherry', 'mango', 'pineapple', 'papaya']
"""
```

**extend()** funciona inclusive com outros objetos iteráveis como [tuplas](./Tuples.md) ou [dicionários](./Dictionary.md). O resultado final continua sendo uma lista.

```python
thislist = ["apple", "banana", "cherry"]
thistuple = ("kiwi", "orange")

thislist.extend(thistuple)

print(thislist)
```