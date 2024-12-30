<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [count()](./CountList.md)

# count()

**count()** é uma função que recebe um elemento, e ela devolverá quantas vezes ele aparece em uma lista.

Lembrando que ele é um método de lista, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
fruits = ["apple", "banana", "cherry", "banana"]

x = fruits.count("banana")

print(x) #Retornará 2
```