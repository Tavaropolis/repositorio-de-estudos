<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Generator Expression](./GeneratorExpression.md)

# Generator Expression

Existe uma forma mais simples de se declarar um [generator](./Generators.md), através das `generators expression`. A declaração funciona de maneira similar a [list comprehension](./ListComprehension.md), porém declarada dentro de um `()` (**Não existe Tuple Comprehension no Python**).

Por debaixo dos panos, o [python](./Index.md) criará uma função generator.

```python
gen = (x**2 for x in range(5))  # Generator Expression

for x in gen:
    print(x)
"""
Saída:
1
4
9
16
"""
```
