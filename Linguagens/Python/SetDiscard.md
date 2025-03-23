<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [discard()](./SetDiscard.md)

# discard()

`discard()` é um método de [set](./Set.md) que permite retirar um elemento do conjunto. Ele funciona de maneira similar ao [`remove()`](./SetRemove.md), a diferença entre as funções é que, o `discard()` não gera um erro caso a chave não exista, ao contrário do `remove()` que gera erro. 

Lembrando que `discard()` é um método da classe Set, você precisa ter uma variável do tipo Set para poder utilizá-lo.

```python
thisset = {"apple", "banana", "cherry"}

thisset.discard("banana")

print(thisset) #Saída {"apple", "cherry"}
```