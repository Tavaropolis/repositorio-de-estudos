<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Int](./Int.md)

# Int

O tipo int corresponde a valores númericos sem casa decimal, podendo ser positivos ou negativos.

```python
x = 5
y = -4

print(type(x))  # <class 'int'>
print(type(y))  # <class 'int'>
```
Um truque interessante do interpretador Python é que vc pode separar os números de um inteiro grande com underlines(_) e o interpretador continua entendendo como número.

```python
x = 1_000_000
print(x) #Saída 1000000
```