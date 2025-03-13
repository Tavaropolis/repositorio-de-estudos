<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Concatenação de Listas](./ListConcat.md)

# Concatenação de Listas

Uma forma bem simples de juntar duas listas é concatenando elas, assim como se faria com uma string, através de um sinal de **+**. Segue exemplo:

```python
list1 = ["a", "b", "c"]
list2 = [1, 2, 3]

list3 = list1 + list2
print(list3) #Retornará ['a', 'b', 'c', 1, 2, 3]
```