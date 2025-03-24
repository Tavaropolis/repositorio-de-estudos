<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [union()](./SetUnion.md)

# union()

`union()` é um método de [set](./Set.md) que retorna um set com a união dos dois ou mais conjuntos (sem repetir os valores, obviamente).

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.union(y) 

print(z) #Saída: {'google', 'cherry', 'microsoft', 'apple', 'banana'}
```

É possível também ser chamado através do operador `|`:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x | y 

print(z) #Saída: {'google', 'cherry', 'microsoft', 'apple', 'banana'}
```

É possível unir mais do que apenas dois conjuntos: 

```python
w = {"meta", "nvidia"}
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.union(y, w) #Unindo com union()
z = w | x | y #Unindo com |

print(z) #Saída {'microsoft', 'apple', 'banana', 'nvidia', 'google', 'meta', 'cherry'}
```

O conjunto original não é alterado na chamada do método.

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

x.union(y)

print(x) #Saída: {'apple', 'cherry', 'banana'}
```