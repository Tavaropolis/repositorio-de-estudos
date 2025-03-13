<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [insert()](./ListInsert.md)

# insert()
**insert()** é uma função que nos possibilita adicionar um elemento em uma lista, e ao contrário do [append()](./AppendList.md), ele pode ser adicionado em qualquer índice.

A função recebe dois parâmetros, o primeiro é o índice, e o segundo o valor que se deseja adicionar.

Lembrando que ele é um método de lista, ou seja é necessário ter uma lista instanciada para poder usar.

```python
thislist = ["apple", "banana", "cherry"]
thislist.insert(1, "orange")
print(thislist) # ['apple', 'orange', 'banana', 'cherry']
```