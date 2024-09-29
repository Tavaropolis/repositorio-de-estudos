<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [BinarioOctalHexadecimal](./BinarioOctalHexadecimal.md)

# Binário, Octal e Hexadecimal
 Além da base padrão decimal da matemática, existem outras três sistemas númericos muito úteis no mundo da computação: binário, octal e hexadecimal.

Binário é o sistema composto por 0 e 1, aqui o número "2" seria o equivalente ao "10", ou seja ao chegar no "2", se vira uma casinha de números, em binário 011 representa o número 3. 

A escala binária é muito útil em programação pois a representação básica de dado em um computador é o bit, ou seja uma unidade composta de 0 ou 1. Oito bits equivalem a um byte.

Em Python, é possível declarar um número binário utilizando o prefixo **0b**. O interpretador Python irá comprender como um número decimal conforme o exemplo abaixo.
```python
binario = 0b1010  # Equivale a 10 em decimal
print(binario)    # Saída: 10
```
É possível utilizar a função **bin()** para converter um valor decimal em um binário.
```python
decimal = 10
binario = bin(decimal)
print(binario)  # Saída: '0b1010'
```

A outra escala númerica é a octal, onde as unidades correspondem a valores de 0 a 7. É possível definir números no Python através do prefixo **0o**, e assim como binário o interpretador entende como número decimal.
```python
octal = 0o12  # Equivale a 10 em decimal
print(octal)  # Saída: 10
```

É possível utilizar a função **oct()** para converter um valor decimal em octal.
```python
decimal = 10
octal = oct(decimal)
print(octal)  # Saída: '0o12'
```

Por fim a última escala é a hexadecimal, nessa escala as unidades compreendem de 0 a 14, como no sistema decimal os números acabam depois do 9, a escala hexadecimal se utiliza de letras: A corresponde a 10, B a 11, C a 12, D a 13, E a 14 e F a 15.

Hexadecimais são úteis para simplificar valores binários. Um hex equivale a 16 ou seja, 4 bits. Para simplicar um valor de byte como **11111111** (255 em decimal), podemos representar em hexadecimal como **FF** ou seja os quatro primeiros bits "valendo" 16, ou seja 1111, a mesma lógica valendo para os quatro últimos.

PAra criar um número em hexadecimal no Python
```python
hexadecimal = 0x1A  # Equivale a 26 em decimal
print(hexadecimal)  # Saída: 26
```

É possível utilizar a função **hex()** para converter valores decimais em hexadecimal.
```python
decimal = 26
hexadecimal = hex(decimal)
print(hexadecimal)  # Saída: '0x1a'
```

É possível converter os valores para decimal se eles forem do tipo texto. Vou falar mais de casting no futuro, mas fica aqui a referência de como fazer a conversão das bases no Python

```python
binario_str = '1010'
decimal = int(binario_str, 2)
print(decimal)  # Saída: 10

octal_str = '12'
decimal = int(octal_str, 8)
print(decimal)  # Saída: 10

hexadecimal_str = '1A'
decimal = int(hexadecimal_str, 16)
print(decimal)  # Saída: 26
```