<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Walrus Operator](./WalrusOperator.md)

# Walrus Operator

Em algumas linguagens como C a atribuição (=) também funcionam dentro de outras estruturas. Por exemplo esse código em C

Aqui, x está recebendo o valor de y dentro de um if. Sendo assim, ambas as variáveis valem 8, e 8 == 8 retorna uma condição verdadeira, executando o código do bloco.
```C
int x = 3, y = 8;

if(x = y) {
    printf("x and y are equal (x = %d, y = %d)", x, y);
}
``` 

O Walrus Operator **(:=)** é um recurso adicionado a partir do Python 3.8 que permite exatemente isso, atribuição de variáveis em situações que não são comumente possível. A declaração mais simples com um operador Walrus seria a seguinte, note que o operador obrigatóriamente tem de estar em um parenteses: 

```python
(walrus := True)
print(walrus) #Saída True
``` 

Reescrevendo aquele código inicial do C para o Python, teríamos isso:
```python
x = 4
y = 8

if(x := y):
    print(f"x: {x}; y: {y}") #Saída x: 8; y: 8
```

Um uso mais uso para o Walrus é parar criar variáveis dentro de dicionários Python.

Sem utilizar Walrus:
```python
numbers = [2, 8, 0, 1, 1, 9, 7, 7]

description = {
    "length": len(numbers),
    "sum": sum(numbers),
    "mean": sum(numbers)/len(numbers)
}

print(description) #Saída {'length': 8, 'sum': 35, 'mean': 4.375}
```

Utilizando Walrus:
```python
numbers = [2, 8, 0, 1, 1, 9, 7, 7]

description_walrus = {
    "length": (num_len := len(numbers)),
    "sum":  (num_sum := sum(numbers)),
    "mean": num_sum/num_sum
}

print(description) #Saída {'length': 8, 'sum': 35, 'mean': 4.375}
print(f"num_len: {num_len}") #Saída num_len: 8
print(f"num_sum: {num_sum}") #Saída num_sum: 35
``` 