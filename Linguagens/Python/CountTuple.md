<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [count()](./CountTuple.md)

# count()

Assim como o **count()** de [listas](./List.md), essa função conta o número de um determinado elemento dentro de uma tupla, basta passar o valor desejado como argumento.

Lembrando que ele é um método de tupla, ou seja é necessário ter uma tupla instanciada para poder usar. Segue exemplo:

```python
thistuple = (1, 3, 7, 8, 7, 5, 4, 6, 8, 5)

x = thistuple.count(5)

print(x) #Irá retornar 2
```