<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [len()](./Len.md)

# len()

**len()** é uma função do Python utilizada para retornar a quantidade de números em uma lista ou coleção. Pode ser utilizada em diversos tipos de dados. 

**len()** pode ser utilizado em strings e ela devolverá o número de caracteres dentro dela. Lembrando que os espaços entre palavras será contado como carácter.

```python
frase = "Esse é o meu jeito ninja"
print(len(frase)) #Irá retornar 24

frase_vazia = ""
print(len(frase_vazia)) #Irá retornar 0
```

Pode ser utilizado em uma lista para devolver o número de elementos. É um dos usos mais comuns.

```python
ninjas = ["Naruto", "Sasuke", "Sakura"]
print(len(ninjas)) #Irá retorna 3

lista_vazia = []
print(len(lista_vazia)) #Irá retorna 0
```

Com [tuplas](./Tuple.md) funciona da mesma maneira que com as listas.

```python
ninjas = ("Naruto", "Sasuke", "Sakura")
print(len(ninjas)) #Irá retorna 3

tupla_vazia = ()
print(len(tupla_vazia)) #Irá retorna 0
```

Com [dicionários](./Dict.md) ele retonará o número de chaves valor, ou seja cada conjunto de chave valor conta como um elemento.

```python
print(len({"James": 10, "Mary": 12, "Robert": 11})) #Retornará 3

len({}) #Retornará 0
```