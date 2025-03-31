<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Dict](./DictComprehension.md)

# Dict Comprehension

Funciona de maneira similar a [list comprehension](./ListComprehension.md) e [set comprehension](./SetComprehension.md), porém trabalhando com chaves e valores.

```python
quadrados = {x: x**2 for x in range(5)}
print(quadrados)  
# Saída: {0: 0, 1: 1, 2: 4, 3: 9, 4: 16}
```

