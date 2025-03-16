<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Acessando o set](./SetAcessando.md)

# Acessando o set

Um [set](./Set.md) é uma coleção não indexada, ou seja, não podemos acessar um elemento de um set através de seu índice como em uma [lista](./List.md). Em um set só podemos percorrer os valores através de um laço [for](./For.md) ou verificando se o elemento existe via [operador in ou not in](./innotinOperator.md).

Percorrendo um `set` com `for`: 
```python
thisset = {"apple", "banana", "cherry"}

for x in thisset:
  print(x)
```

Verificando se o elemento existe com o `operador in`:
```python
thisset = {"apple", "banana", "cherry"}

print("banana" in thisset) #Retorna True
```

Verificando se o elemento não existe com o `operador not in`:
```python
thisset = {"apple", "banana", "cherry"}

print("banana" not in thisset) #Retorna False
```