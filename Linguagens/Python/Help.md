<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [help()](./Help.md)

# help()
**help()** é uma função build-in do Python que retorna uma breve descrição sobre as funções. Segue um exemplo:

```python
help(print) #Retorna uma breve descrição da função
```
O interessante é que o **help()** se baseia em doc string, você pode adicionar textos as funções para que este seja desenvolvida quando o for chamada dentro do help.

```python
def saudacao(nome):
    """
    Esta função exibe uma saudação personalizada para o nome fornecido.
    
    Parâmetros:
    nome (str): O nome da pessoa para quem a saudação será feita.
    
    Retorna:
    str: Uma saudação personalizada.
    """
    return f"Olá, {nome}!"

help(saudacao)
```

Além de funções podemos chamar a função **help()** para uma classe, bem como definir uma doc string caso a classe seja chamada dentro de um **help()**.

```python
class Carro:
    """
    A classe Carro simula um carro básico.
    
    Atributos:
    modelo (str): O modelo do carro.
    cor (str): A cor do carro.
    """

    def __init__(self, modelo, cor):
        self.modelo = modelo
        self.cor = cor

    def ligar(self):
        """
        Método para ligar o carro.
        
        Retorna:
        str: Mensagem indicando que o carro foi ligado.
        """
        return "Carro ligado!"

help(Carro)
```

Por fim ainda é possível chamar o **help()** para um módulo, além de adicionar um docstring para explicar a função do módulo.

```python
"""
Este módulo contém funções e classes para manipulação de carros.
"""

class Carro:
    """
    A classe Carro simula um carro básico.
    """
    def __init__(self, modelo, cor):
        self.modelo = modelo
        self.cor = cor
```