<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [sort()](./SortList.md)

# sort()

**sort()** é uma função do Python capaz de organizar uma lista, alfabéticamente ou númericamente. 

Importante notar que **sort()** é um método de lista, e não uma buildin do Python, é necessário então primeiro criar uma lista e então chamar o método dela (algo como por exemplo sualista.sort()).

```python
ninjas = ["Sasuke", "Naruto", "Sakura", "Kakashi"]

ninjas.sort()

print(ninjas) #['Kakashi', 'Naruto', 'Sakura', 'Sasuke']
```

**sort()** aplicado em uma lista de números:
```python
thislist = [100, 50, 65, 82, 23]

thislist.sort()

print(thislist) #[23, 50, 65, 82, 100]
```

Importante dizer que a lista deve conter apenas números ou apenas strings, caso os dois tipos existam na lista e o **short()** seja invocado, irá ser retornado um erro.

## sort() decrescente
Para se organizar a lista em ordem decrescente, basta utilizar o parâmetro reverse = True. Segue exemplos:

```python
ninjas = ["Sasuke", "Naruto", "Sakura", "Kakashi"]

ninjas.sort(reverse = True) 

print(ninjas) #['Sasuke', 'Sakura', 'Naruto', 'Kakashi']
```

Reverse aplicada a uma lista númerica
```python
thislist = [100, 50, 65, 82, 23]

thislist.sort(reverse = True)

print(thislist) #[100, 82, 65, 50, 23]
```