<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Set](./SetComprehension.md)

# Set Comprehension

Funciona de maneira semelhante as [list comprehensions](./ListComprehension.md), onde podemos fazer um set completo rapidamente com uma linha de comando. A única diferença é que valores repetidos não serão inseridos no set. 

O **set comprehension** tem de ser declarado dentro de um `{}` Segue o exemplo: 

```python
numeros = [1, 2, 2, 3, 4, 5]
quadrados = {x**2 for x in numeros}

print(quadrados)  # {1, 4, 9, 16} 
```

É ainda possível adicionar um critério para os elementos do set com um `if`: 

```python
numeros = [1, 2, 3, 4, 5]
quadrados = {x**2 for x in numeros if x % 2 == 0} #Selecionando apenas os pares

print(quadrados)  # {1, 4, 9, 16}
```

É possível também rodar um **set comprehension** em matrizes, basta utilizar mais de um `for in`:

```python
this_list = [[1, 2, 3], [4, 5, 6], [7, 8,9]]

res_list = {val for num in this_list for val in num}

print(res_list)
```