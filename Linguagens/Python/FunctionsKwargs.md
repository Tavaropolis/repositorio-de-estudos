<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [**kwargs](./FunctionsKwargs.md)

# **kwargs
Funciona semelhante ao [`*args`](./FunctionsArgs.md), porém com a diferença que o `**kwargs` se aplica a quando queremos passar um número variável de parâmetros nomeados. Para definir uma [função*](./Functions.md) com `**kwargs` basta colocar um `**` antes do parâmetro na definição. A função recebe o `**kwargs` como um [dict](./Dict.md):

```python
def informacoes(**dados):
    for chave, valor in dados.items():
        print(f"{chave}: {valor}")

informacoes(nome="Ana", idade=22, cidade="São Paulo")
# Saída:
# nome: Ana
# idade: 22
# cidade: São Paulo
```
Assim como acontece com os `*args`, o `**kwargs` não precisa ser o único parâmetro de uma **função**, ele pode ser combinado com parâmetros posicionais, nomeados e até um `*args`:

`**kwargs` com parâmetro nomeados, **(é necessário que o `*args` seja o último parâmetro)**:
```python
def minha_funcao(extra=0, **kwargs):
    print("Extra:", extra)
    print("Kwargs:", kwargs)

# Chamadas válidas
minha_funcao(a=1, b=2)  # Extra usa o valor padrão (0)
# Saída: Extra: 0 | Kwargs: {'a': 1, 'b': 2}

minha_funcao(extra=10, a=1, b=2)  # Extra modificado
# Saída: Extra: 10 | Kwargs: {'a': 1, 'b': 2}
```

`**kwargs` e parâmetros posicionais:

```python
def minha_funcao(primeiro, **kwargs):
    print("Primeiro argumento:", primeiro)
    print("Kwargs:", kwargs)

# Chamadas válidas
minha_funcao(10, a=1, b=2)  
# Saída: Primeiro argumento: 10 | Kwargs: {'a': 1, 'b': 2}

# Chamadas inválidas
minha_funcao(a=1, b=2)  # ERRO: falta o argumento posicional 'primeiro'
```

`**kwargs` com um parâmetro nomeado e um `*args`:
```python
def minha_funcao(*args, extra=0, **kwargs):
    print("Args:", args)
    print("Extra:", extra)
    print("Kwargs:", kwargs)

# Chamadas válidas
minha_funcao(1, 2, 3, extra=10, nome="Carlos", idade=25)
# Saída:
# Args: (1, 2, 3)
# Extra: 10
# Kwargs: {'nome': 'Carlos', 'idade': 25}
```