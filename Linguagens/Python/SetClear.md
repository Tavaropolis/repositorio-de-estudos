<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [clear()](./SetClear.md)

# clear()

Funciona da mesma maneira que o `clear()` nas [listas](./ListClear.md) e [tuplas](./TupleClear.md). Essa função permite retirar todos os elementos de um conjunto, o deixando completamente vazio.

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
thisset = {"apple", "banana", "cherry"}

thisset.clear()

print(thisset) #Saída: set()
```