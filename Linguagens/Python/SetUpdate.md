<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [update()](./SetUpdate.md)

# update()

O método **update()** funciona de maneira semelhante a [concatenação de lista](./ListConcat.md). Aqui se junta uma [coleção](./Index.md#coleções) a um **set** já existente. Lembre que por ser um método da classe **set** é preciso ter uma variável **set** definida.

```python
thisset = {"apple", "banana", "cherry"}
tropical = {"pineapple", "mango", "papaya"} #Adicionando set
mylist = ["kiwi", "orange"] # Adicionando lista

thisset.update(tropical)

print(thisset)
```