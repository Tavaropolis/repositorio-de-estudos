<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [symmetric_difference()](./SetSymmetricDifference.md)

# symmetric_difference()

`symmetric_difference()` é um método de [set](./Set.md) que retorna um conjunto que é a união de dois conjuntos, tirando a intersecção entre eles.

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.symmetric_difference(y) 

print(z) #Saída: {'banana', 'cherry', 'microsoft', 'google'}
```

É possível também ser chamado através do operador `^`:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x ^ y

print(z) #Saída: {'banana', 'cherry', 'microsoft', 'google'}
```

O conjunto original não é alterado na chamada do método.

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

x.symmetric_difference(y) 

print(x) #Saída: {"apple", "banana", "cherry"}
```