<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [intersection()](./SetIntersection.md)

# intersection()

`intersection()` é um método de [set](./Set.md), que verifica dois conjuntos e retorna os elementos que existam nos dois elementos, literalmente a intersecção de dois conjuntos.

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.intersection(y) 

print(z) # Saída: {"apple"}
```

É possível também ser chamado através do operador `&`:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x & y 

print(z) # Saída: {"apple"}
```

O conjunto original não é alterado na chamada do método.

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

x.intersection(y) 

print(x) #Saída: {'apple', 'banana', 'cherry'}
```