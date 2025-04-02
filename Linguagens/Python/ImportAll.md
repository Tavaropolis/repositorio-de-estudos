<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Import All](./ImportAll.md)

# \_\_all\_\_

A variável `__all__` é uma lista de strings que define quais nomes serão exportados quando `from module import *` é usado. Isso ajuda a controlar quais nomes são expostos quando se usa importação com `*`.

Para utilizar o `__all__` basta criar um módulo [python](./Index.md), no nosso exemplo ele será chamado `meu_modulo.py`:

```python
# meu_modulo.py

# Definindo quais nomes serão exportados
__all__ = ['somar', 'multiplicar']

def somar(a, b):
    return a + b

def multiplicar(a, b):
    return a * b

def dividir(a, b):
    return a / b
```

Agora, quando importarmos usando `*`, apenas as funções listadas em `__all__` estarão disponíveis:

```python
from meu_modulo import *

# Estas funções estão disponíveis
print(somar(2, 3))      # 5
print(multiplicar(2, 3)) # 6

# A função dividir() NÃO está disponível, pois não está em __all__
# print(dividir(6, 2))   # NameError: name 'dividir' is not defined
```

## Importação sem __all__

Se `__all__` não for definido, o Python exportará todos os nomes que **não começam com underscore**:

```python
# modulo_sem_all.py

def funcao1():
    return "Função 1"

def funcao2():
    return "Função 2"

def _funcao_privada():
    return "Função privada"
```

```python
from modulo_sem_all import *

# Todas as funções públicas estão disponíveis
print(funcao1())  # "Função 1"
print(funcao2())  # "Função 2"

# A função privada não está disponível
# print(_funcao_privada())  # NameError: name '_funcao_privada' is not defined
```

## Importação com classes

`__all__` também funciona com classes:

```python
# classes.py

__all__ = ['Pessoa', 'Animal']

class Pessoa:
    def __init__(self, nome):
        self.nome = nome

class Animal:
    def __init__(self, especie):
        self.especie = especie

class Carro:
    def __init__(self, modelo):
        self.modelo = modelo
```

```python
from classes import *

# Estas classes estão disponíveis
pessoa = Pessoa("João")
animal = Animal("Cachorro")

# A classe carro NÃO está disponível
# carro = Carro("Fusca")  # NameError: name 'Carro' is not defined
```

## Importação com variáveis

`__all__` também controla a exportação de variáveis:

```python
# variaveis.py

__all__ = ['PI', 'GRAVIDADE']

PI = 3.14159
GRAVIDADE = 9.81
E = 2.71828
```

```python
from variaveis import *

# Estas variáveis estão disponíveis
print(PI)       # 3.14159
print(GRAVIDADE) # 9.81

# Esta variável NÃO está disponível
# print(E)      # NameError: name 'E' is not defined
```

## Boas práticas

1. Sempre defina `__all__` em módulos que podem ser importados com `*`
2. Mantenha a lista de `__all__` atualizada quando adicionar ou remover nomes do módulo
3. Use `__all__` para documentar explicitamente a API pública do seu módulo
4. Evite usar `import *` em código de produção, prefira importações explícitas



