<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [add()](./SetAdd.md)

# add()

**add()** é um dos métodos de **set** para adicionar um novo elemento. Por ser um método da classe **set** é necessário ter uma variável declarada:

```python
thisset = {"apple", "banana", "cherry"}

thisset.add("orange")

print(thisset)
```

Adicionar um elemento que já exista no **set** não ocasionará erro, porém nada será adicionado.

```python
thisset = {"apple", "banana", "cherry"}

thisset.add("apple")

print(thisset) #Não irá gerar erro
```