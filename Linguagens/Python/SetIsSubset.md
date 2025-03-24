<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [issubset()](./SetIsSubset.md)

# issubset()

`issubset()` é um método de [set](./Set.md), que verifica se um set está incluso em outro set, ou seja se ele é um subconjunto. O retorno do `issubset()` é um [Bool](./Bool.md).

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b", "a"}

z = x.issubset(y) #Verifica se x é subconjunto de y

print(z) #Saída: True
```

É possível também ser chamado através do operador `<=`:

```python
x = {"a", "b", "c"}
y = {"f", "e", "d", "c", "b", "a"}

z = x <= y 

print(z)  #Saída: True
```