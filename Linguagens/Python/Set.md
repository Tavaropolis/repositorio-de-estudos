<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Set](./Set.md)

# Set

Um **set** é um tipo de coleção do [Python](./Index.md) que se assemelha a uma [lista](./List.md), com duas grandes diferenças: **set não permitem elementos repetidos e os elementos não são ordenados por índices**.

Podemos declarar um novo **set** através da notação com `{}`. Segue o exemplo: 
```python
thisset = {"apple", "banana", "cherry", "apple"}

print(thisset)
```

Também é possível iniciar um novo **set** através do construtor `set()`. Note que o construtor recebe uma [coleção](./Index.md#coleções):

```python
thisset = set(("apple", "banana", "cherry")) #Recebendo uma tupla

thisset2 = set(["apple", "banana", "cherry"]) #Recebendo uma lista

print(thisset)
print(thisset2)
```

**Sets** podem ser compostos de diferentes tipos de dados: 

```python
set1 = {"apple", "banana", "cherry"}
set2 = {1, 5, 7, 9, 3}
set3 = {True, False, False}
set4 = {"abc", 34, True, 40, "male"}
```

Ao contrário das listas, **Sets** não são indexados, tentar recuperar um valor pelo índece irá ocasionar um `TypeError`: 

```python
thisset = {"apple", "banana", "cherry", "apple", "banana"}

print(thisset[0]) #TypeError: 'set' object is not subscriptable
```
## Retorno do type()
Se aplicado um `type()` a um elemento do tipo **set**, verá que eles são considerados da **classe set**.

```python
myset = {"apple", "banana", "cherry"}
print(type(myset)) #Retornará <class 'set'>
```