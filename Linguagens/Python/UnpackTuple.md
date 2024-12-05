<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Desempacotamento de Tuplas](./UnpackTuple.md)

# Desempacotamento de Tuplas

O ato de passar valores para uma tupla muitas vezes é chamado de **empacotamento** (packing). O ato de retirar valores de uma tupla e joga-los em uma variável, portanto, é chamado de **desempacotamento** (unpacking).

O **desempacotamento** mais simples de se fazer é de apenas definir as variáveis e usar o sinal de igual a tupla. Segue o exemplo:

```python
fruits = ("apple", "banana", "cherry")

(green, yellow, red) = fruits

print(green) #apple
print(yellow) #banana
print(red) #cherry
```

## Desempacotamento com asterísco *

O asterísco é um operador utilizado para retirar parte da tupla como [lista](./List.md). O Python separa on índices sem asterísco e cria uma lista com o resto. Segue exemplos:

```python
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")

(green, yellow, *red) = fruits

print(green) #apple
print(yellow) #banana
print(red) #['cherry', 'strawberry', 'raspberry']
``` 

```python
fruits = ("apple", "banana", "cherry", "strawberry", "raspberry")

(green, yellow, *red, pink, black) = fruits

print(green) #apple
print(yellow) #banana
print(red) #['cherry']
```