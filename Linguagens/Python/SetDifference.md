<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [difference()](./SetDifference.md)

# difference()

`difference()` é um método de [set](./Set.md) que compara dois conjuntos e retorna os elementos do primeiro que não estão presentes no segundo. É como se você estivesse fazendo uma subtração de dois conjuntos, onde o conjunto passado como argumento do `difference()` está subtraindo os elementos do primeiro conjunto.

Lembrando que ele é um método de Set, ou seja é necessário ter uma lista instanciada para poder usar. Segue exemplo:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x.difference(y) 

print(z) #Saída {'cherry', 'banana'}
```

É possível também ser chamado através do operador `-`:

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

z = x - y 

print(z) #Saída {'cherry', 'banana'}
```

O conjunto original não é alterado na chamada do método.

```python
x = {"apple", "banana", "cherry"}
y = {"google", "microsoft", "apple"}

x.difference(y) #x não será alterado

print(x) #Saída: {'banana', 'apple', 'cherry'}
```