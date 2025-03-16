<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [List Comprehension](./ListComprehension.md)

# List Comprehension

Um recurso bem único do Python é de gerar listas com apenas uma linha de código através de uma técnica chamada **list comprehension**.

Segue um exemplo simples onde se cria uma segunda lista

```python
numeros = [1, 2, 3, 4, 5]
quadrados = [x**2 for x in numeros]

print(quadrados)  # [1, 4, 9, 16]
```

Pode ser utilizado para criar uma lista com vários elementos de texto iguais (O `_` indica que a variável temporária não é importante):
```python
naruto_list = ["Naruto" for _ in range(3)]

print(naruto_list) #Saída: ['Naruto', 'Naruto', 'Naruto']
```

É ainda possível adicionar um critério para os elementos da lista com um `if`: 

```python
numeros = [1, 2, 3, 4, 5]
quadrados = [x**2 for x in numeros if x % 2 == 0] #Selecionando apenas os pares

print(quadrados)  # [1, 4, 9, 16]
```

É possível também rodar uma **list comprehension** em matrizes, basta utilizar mais de um `for in`:

```python
this_list = [[1, 2, 3], [4, 5, 6], [7, 8,9]]

res_list = [val for num in this_list for val in num]

print(res_list)
```