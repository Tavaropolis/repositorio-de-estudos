<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [self](./SelfClass.md)

# self

**self** é uma das palavras reservadas do Python. Ela é utilizada dentro do contexto de orientação, dentro de um construtor. Ele representa a instância atual da classe (assim como o **this** no Java).

Veja o exemplo abaixo: para p o this é o objeto "Alice" e para p2 o objeto "Bob".

```python
class Pessoa:
    def __init__(self, nome, idade):
        self.nome = nome  # Atributo da instância
        self.idade = idade

p1 = Pessoa("Alice", 25)
p2 = Pessoa("Bob", 44)
```

Um ponto interessante é que o **self** pode receber qualquer nome e ainda funciona. Mas por convenção é melhor deixar como **self**.

```python
class Pessoa:
    def __init__(instancia, nome, idade):
        instancia.nome = nome  # Atributo da instância
        instancia.idade = idade
```