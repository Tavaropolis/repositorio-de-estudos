<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [remove()](./RemoveList.md)

# remove()

Uma das formas para remover um item de uma lista é através da função **remove()**. Ela retira um item com base no valor. 

Lembrando que ele é um método de lista, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
konoha = ["Naruto", "Sasuke", "Sakura"]

konoha.remove("Sasuke")

print(konoha) #Sasuke não está mais na lista
``` 

Caso tenha mais de um mesmo elemento na lista, o **remove()** irá retirar o primeiro.

```python
thislist = ["apple", "banana", "cherry", "banana", "kiwi"]

thislist.remove("banana")

print(thislist) #Só foi retirada a primeira
```