<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [List](./List.md)

# List
Um **list** é um tipo de dado em que se pode salvar mais de uma informação ao mesmo tempo, literalmente uma lista. Em algumas linguagens essa estrutura é chamada de **array**.

Segue um exemplo de como se declarar uma lista em python:
```python
ninjas = ["Naruto", "Sasuke", "Sakura"]
```

Outra possível forma de se declarar uma lista é através do construtor **list()** (veremos mais detalhes disso no tópico de orientação a objetos).
```php
list1 = list(("apple", "banana", "cherry"))
```

Uma lista pode receber dados de qualquer tipo, ou mesmo de tipos diferentes:
```python
list1 = ["apple", "banana", "cherry"]
list2 = [1, 5, 7, 9, 3]
list3 = [True, False, False]
list4 = ["abc", 34, True, 40, "male"]
```

Os valores recebem indíces começando do 0. Para acessar um valor da lista basta colcoar o valor do índice entre colchetes **([ ])**. Segue exemplo:

```python
ninjas = ["Naruto", "Sasuke", "Sakura"]
print(ninjas[0]) #Printa "Naruto"
```

Se utilizado um type() em uma lista, o python retornará **<class 'list'>**.

```python
mylist = ["apple", "banana", "cherry"]
print(type(mylist)) #Printa <class 'list'>
```