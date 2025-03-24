<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [issuperset()](./SetIsSuperset.md)

# issuperset()

`issuperset()` é a função oposta do [`issubset()`](./SetIsSubset.md). Essa função verifica se um conjunto é um superconjunto do outro. O `superset()` retorna um [Bool](./Bool.md).

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
x = {"f", "e", "d", "c", "b", "a"}
y = {"a", "b", "c"}

z = x.issuperset(y) 

print(z) #Saída: True
```

É possível também ser chamado através do operador `>=`:

```python
x = {"f", "e", "d", "c", "b", "a"}
y = {"a", "b", "c"}

z = x >= y

print(z) #Saída: True
```