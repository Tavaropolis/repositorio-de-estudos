<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [*args](./FunctionsArgs.md)

# *args
`*args` é para parâmetros posicionais variados. Para criar uma [função](./Functions.md) com `*args` basta colocar um `*` antes do nome do parametro. Um `*args` é recebido pela função como uma [tupla](./Tuple.md).

```python
def soma_tudo(*numeros):
    return sum(numeros)

print(soma_tudo(1, 2, 3, 4))  # Saída: 10
```

Você pode combinar `*args` com parâmetros posicionais ou parâmetros nomeados. **O `*args` não precisa ser o único parâmetro na função**:

`*args` com parâmetro nomeado em uma função:
```python
def somar_numeros(*numeros, multiplicador=1):
    soma = sum(numeros)
    return soma * multiplicador

# Testando a função
print(somar_numeros(1, 2, 3))  # Saída: 6 (multiplicador padrão = 1)
print(somar_numeros(1, 2, 3, multiplicador=2))  # Saída: 12 (multiplicador = 2)
```

`*args` com parametro posicional **(é necessário que o `*args` seja o último parâmetro)**:

```python
def minha_funcao(primeiro, *args):
print("Primeiro argumento:", primeiro)
print("Args:", args)

# Agora o primeiro argumento sempre será posicional
minha_funcao(10, 1, 2, 3)  
# Saída:
# Primeiro argumento: 10
# Args: (1, 2, 3)
```

Juntando `*args`, parâmetros opcionais e parâmetros nomeados: 

```python
def minha_funcao(primeiro, *args, extra=0):
print("Primeiro argumento:", primeiro)
print("Args:", args)
print("Extra:", extra)

# Chamadas válidas
minha_funcao(10, 1, 2, 3)  # Extra usa o valor padrão (0)
minha_funcao(10, 1, 2, 3, extra=5)  # Extra alterado
```