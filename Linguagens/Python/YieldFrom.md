<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [yield from](./YieldFrom.md)

# yield from

Quando trabalhamos com [generators](./Generators.md) temos a opção de retornar a pausa dos `yield` a partir de outro generator. Para isso utilizamos a palavra reservada `yield from`:

```python
def gen1():
    yield 1
    yield 2
    yield 3
    
def gen2():
    yield from gen1() #Vai começar a partir do último yield do gen1()
    yield 4
    yield 5
    yield 6

g = gen2()

for x in g:
    print(x)

"""
Saída: 
1
2
3
4
5
6
"""
```