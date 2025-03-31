<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [isinstance()](./IsInstance.md)

# Truthy e Falsy

Existem alguns valores específicos que o [Python](./Index.md) implicitamente converte em `False` se estiverem dentro de um bloco [if](./ifElifElse.md). Esses valores são conhecidos como **Falsy**. Segue a lista de dados que o Python considera **Falsy**:

```python
#Valores que o Python considera Falsy
lista = []
dicionario = {}
conjunto = set()
tupla = ()
string = ''
inteito = 0
flutuante = 0.0
nada = None
falso = False
intervalo = range(0)
```

Em contrapartida, todos os dados que não sejam os acima, são os **Truthy**, ou seja, o bloco if entenderia como verdadeiro.