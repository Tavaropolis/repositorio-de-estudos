<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Tuple](./Tuple.md)

# Tuplas

As **Tuplas** são uma das estruturas de coleção do Python. É muito similar as [listas](./List.md) porém com uma grande diferença, as **tuplas** são imutáveis. Ou seja, não podemos adicionar, remover ou modificar os valores de uma tupla.

## Declarando uma tupla
**Tuplas** são declaradas através do uso de parênteses.

```python
ninjas = ("Naruto", "Sasuke", "Sakura")
print(type(ninjas)) #<class 'tuple'>
```

É criar através do construtor **tuple** também, só precisa se tomar um pouco de cuidado, pois a síntaxe utiliza dois parênteses.

```python
ninjas = tuple(("Naruto", "Sasuke", "Sakura"))
print(type(ninjas)) #<class 'tuple'>
```
Outro cuidado a se tomar é no caso de se criar uma tupla com um único item. Quando se cria direto com parênteses é necessário uma vírgula após o valor.

```python
thistuple = ("apple",)
print(type(thistuple)) #<class 'tuple'>

#Não é uma tupla
thistuple = ("apple")
print(type(thistuple)) #<class 'str'>
```

Com o construtor isso não é necessário.
```python
thistuple = tuple(("apple"))
print(type(thistuple)) #<class 'tuple'>
```
## Tuplas são indexadas

Assim como nas listas, os valores das tuplas também recebem índices iniciando no 0.

```python
ninjas = ("Naruto", "Sasuke", "Sakura")
print(ninjas[0]) #retorna "Naruto"
```

## Tuplas podem possuir valores duplicados 

Assim como listas, as **tuplas** aceitam valores duplicados.

```python
ninjas = ("Naruto", "Sasuke", "Sakura", "Sakura") #Não gera erro.
```

## Tuplas aceitam qualquer tipos de dados

Assim como as listas, as **tuplas** aceitam quaisquer tipos da dados, inclusive dados diferentes em uma mesma **tupla**.

```python
tuple1 = ("abc", 34, True, 40, "male") #Não gera erro.
```

## Tuplas são hashables

Por serem imutáveis, as tuplas são consideradas um tipo de dados [hashable](./Hash.md), desde que os elementos internos também sejam.

## Tupas tem melhor desempenho que listas

Por serem estruturas mais simples e imutáveis, elas tem melhor desempenho no código do que listas. 