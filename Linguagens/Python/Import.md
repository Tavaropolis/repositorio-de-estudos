<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Import](./Import.md)

# Import

O sistema de importação do [Python](./Index.md) permite que você reutilize código de outros módulos em seu programa. Isso é fundamental para organizar o código em partes menores e reutilizáveis.

## Import básico

A forma mais simples de importar um módulo é usando a palavra-chave `import`:

```python
import math

# Usando funções do módulo math
print(math.pi)  # 3.141592653589793
print(math.sqrt(16))  # 4.0
```

## Import com alias

Podemos dar um nome alternativo ao módulo usando `as`:

```python
import math as m

# Usando o alias 'm' ao invés de 'math'
print(m.pi)  # 3.141592653589793
print(m.sqrt(16))  # 4.0
```

## Import específico

Podemos importar apenas as funções ou classes que precisamos usando `from ... import`:

```python
from math import pi, sqrt

# Usando as funções diretamente, sem o nome do módulo
print(pi)  # 3.141592653589793
print(sqrt(16))  # 4.0
```

## Import com alias para funções específicas

Podemos combinar o import específico com alias:

```python
from math import sqrt as raiz_quadrada

# Usando o alias para a função
print(raiz_quadrada(16))  # 4.0 (está aplicando math.sqrt())
```

## Import de todos os elementos

Podemos importar todos os elementos de um módulo usando `*`:

```python
from math import *

# Usando todas as funções do módulo diretamente
print(pi)  # 3.141592653589793
print(sqrt(16))  # 4.0
print(sin(0))  # 0.0
```

> **Nota**: O uso de `import *` não é recomendado em código de produção, pois pode tornar difícil identificar de onde vem cada função e pode causar conflitos de nomes.

## Import de módulos personalizados

Podemos criar nossos próprios módulos e importá-los. Por exemplo, se tivermos um arquivo `meu_modulo.py`:

```python
# meu_modulo.py
def somar(a, b):
    return a + b

def multiplicar(a, b):
    return a * b
```

Podemos importá-lo assim:

```python
import meu_modulo

# Usando as funções do nosso módulo
print(meu_modulo.somar(2, 3))  # 5
print(meu_modulo.multiplicar(2, 3))  # 6
```

## Import de pacotes

Um pacote é um diretório que contém módulos Python. Para criar um pacote, precisamos de um arquivo `__init__.py` (pode ser vazio) no diretório. Por exemplo:

```
meu_pacote/
    __init__.py
    modulo1.py
    modulo2.py
```

Podemos importar assim:

```python
from meu_pacote import modulo1, modulo2

# Usando funções dos módulos
print(modulo1.funcao1())
print(modulo2.funcao2())
```

## Import relativo

Dentro de um pacote, podemos usar importação relativa para referenciar módulos do mesmo pacote:

```python
# Dentro de meu_pacote/modulo1.py
from .modulo2 import funcao2  # Importa do mesmo diretório
from ..outro_pacote import modulo3  # Importa do diretório pai
```

## Ordem de importação

É uma boa prática organizar as importações na seguinte ordem:

1. Importações da biblioteca padrão
2. Importações de bibliotecas de terceiros
3. Importações de módulos locais

```python
# 1. Biblioteca padrão
import os
import sys

# 2. Bibliotecas de terceiros
import pandas as pd
import numpy as np

# 3. Módulos locais
from meu_pacote import modulo1
``` 