<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [while](./While.md)

# while

**While** é uma das estruturas mais comuns da programação e é um dos dois laços de repetição do Python (o outro é o [for](./For.md)).

O **while** consiste em um bloco de código que é executado caso a condição do **while** seja verdadeira. Uma vez que todo o código de dentro do bloco é executado, é verificado de a condição **while** ainda é verdadeira, e caso seja, o código é executado novamente.

Por esse motivo, é muito importante criar condições e tomar cuidado para não criar um loop infinito.

```python
i = 1
while i < 6:
  print(i)
  i += 1
```

Exemplo de laço while infinito: 
```python
while True:
    print("Eu sou infinito")
```

## While else
É uma peculiaridade do Python e uma função um pouco inútil, mas você pode definir um else no while que será executando quando a condição do while não é mais verdadeira.

```python
i = 1
while i < 6:
  print(i)
  i += 1
else:
  print("i não é mais menor que 6")
```