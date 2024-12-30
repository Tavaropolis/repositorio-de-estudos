<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [List Comprehension](./ListComprehension.md)

# List Comprehension

Um recurso bem único do Python é de gerar listas com apenas uma linha de código através de uma técnica chamada **list comprehension**.

Segue um exemplo simples onde se cria uma segunda lista

```python
numeros = [1, 2, 3, 4]
quadrados = [x**2 for x in numeros]

print(quadrados)  # [1, 4, 9, 16]
```