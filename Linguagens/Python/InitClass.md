<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [\_\_init\_\_()](./InitClass.md)

# \_\_init\_\_()

É muito comum querermos passar atríbutos já no momento da criação da instância do objeto. Para que possamos fazer isso, no python utilizamos um **innitializer** (em outras linguagens é chamado de contrutor).

O **\_\_init\_\_()** é um magic method ou dunder method (por sempre estarem em volta de dois underlines). São métodos específicos do Python para serem usados em casos especiais. 

Essa função recebe os paramêtros na instânciação e passa aos ao objeto através do [**self**](./SelfClass.md). O **self** representa a instância atual da classe. Note que ele é obrigatório na chamada do **\_\_init\_\_()** e precisa ser o primeiro argumento.

```python
#Definindo a classe
class Pessoa:
    def __init__(self, nome, idade):
        self.nome = nome  # Atributo da instância
        self.idade = idade

#Instânciando o objeto
p = Pessoa("Alice", 25)
print(p.nome)  # Alice
print(p.idade)  # 25
```