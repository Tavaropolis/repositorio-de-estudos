<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Operadores Aritméticos](./Operadores.md)

# Operadores Aritméticos
Uma das coisas mais básicas que se deseja fazer em um script de programação são operações matemáticas. Python oferece algumas opções de operadores, eles são: 

- Adição (+)
- Subtração (-)
- Multiplicação (*)
- Divisão (/)
- Divisão Inteira (//)
- Módulo ou Resto de divisão (%)
- Exponenciação (**)
  
```python
a = 10
b = 3

# Adição
soma = a + b
print(f'{a} + {b} = {soma}')  # Saída: 10 + 3 = 13

# Subtração
subtracao = a - b
print(f'{a} - {b} = {subtracao}')  # Saída: 10 - 3 = 7

# Multiplicação
multiplicacao = a * b
print(f'{a} * {b} = {multiplicacao}')  # Saída: 10 * 3 = 30

# Divisão
divisao = a / b
print(f'{a} / {b} = {divisao}')  # Saída: 10 / 3 = 3.3333333333333335

# Divisão inteira
divisao_inteira = a // b
print(f'{a} // {b} = {divisao_inteira}')  # Saída: 10 // 3 = 3

# Módulo (resto da divisão)
modulo = a % b
print(f'{a} % {b} = {modulo}')  # Saída: 10 % 3 = 1

# Exponenciação
exponenciacao = a ** b
print(f'{a} ** {b} = {exponenciacao}')  # Saída: 10 ** 3 = 1000
```