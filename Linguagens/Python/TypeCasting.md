<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Type Casting](./TypeCasting.md)

# Type Casting

Existem situações onde queremos converter um tipo de dado em outro, esta conversão de dados é chamada de **casting** (ou type casting). Python é uma linguagem orientada a objetos (veremos mais detalhes mais pra frente), mas os tipos primitivos são classes e usamos uma função dela, **o construtor** para converter o tipo do dado. 

Para o casting existe três construtores disponíveis: **int()**, **float()** e **str()**.

## **int()**
**int()** é usado para fazer converção em números inteiros. Caso seja originalmente um float, ele irá perder a casa decimal. Caso a string não seja um número inteiro irá ser gerado um erro.

```python
x: int = int(1)   # x será 1
y: int = int(2.8) # y será 2
z: int = int("3") # z será 3
```

## **float()**
**float()** é usado para converter em números de ponto flutuante. Se o dado for originalmente um número inteiro, será adicionado um .0 a ele (1 se tornará 1.0). Caso a string não seja um número irá ser gerado um erro.

```python
x: float = float(1)     # x será 1.0
y: float = float(2.8)   # y será 2.8
z: float = float("3")   # z será 3.0
w: float = float("4.2") # w será 4.2
``` 

## **str()**
**str()** é utilizado para transformar números em string.

```python
x:str = str("s1") # x será 's1'
y:str = str(2)    # y será '2'
z:str = str(3.0)  # z será '3.0'
```