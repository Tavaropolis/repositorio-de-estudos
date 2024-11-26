<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Acessando Lista](./AcessandoLista.md)

# Acessando a lista
Os valores recebem indíces começando do 0. Para acessar um valor da lista basta colcoar o valor do índice entre colchetes **([ ])**. Segue exemplo:

```python
ninjas = ["Naruto", "Sasuke", "Sakura"]
print(ninjas[0]) #Printa "Naruto"
```

É possível acessar o último valor utilizando o índice -1. E seguindo sucessivamente, -2 retornaria o penulo e assim por diante.

```python
thislist = ["apple", "banana", "cherry"]
print(thislist[-1]) #Retornará "cherry"
print(thislist[-2]) #Retornará "banana"
```

Através dos parenteses é possível selecionar um range de índices. Sendo o primeiro valor o índice inicial e o segundo o final, que não é incluído, ou seja, um range 2:5, retornará os índices: 2, 3 e 4.

```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]

print(thislist[2:5]) #Retornará "cherry", "orange" e "kiwi"
```

Se o valor inicial for 0 é possível omiti-lo do range.

```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]

print(thislist[:4]) #Retornará "apple", "banana", "cherry" e "orange"
```

O mesmo quando queremos range até o último elemento.

```python
thislist = ["apple", "banana", "cherry", "orange", "kiwi", "melon", "mango"]

print(thislist[2:]) #Retornará "cherry", "orange", "kiwi", "melon" e "mango"
```