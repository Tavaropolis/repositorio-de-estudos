<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [isinstance()](./IsInstance.md)

# isinstance()

Além do [`type()`](./Type.md), outra forma de se verificar o tipo de uma variável é através da função `isinstance()`. Ao contrário do `type()`que só retorna o tipo de uma variável, o `isinstance()` vai receber dois argumentos: a variável analisada e um tipo que se deseja ver se ela pertence. Se a variável for tipo avaliado, será retornado `True`, caso não, será retornado `False`.

```python
x = isinstance(5, int)

print(x) #Saída: True
```

É possível passar uma [tupla](./Tuple.md), caso queira avaliar se mais de um tipo: 

```python
x = isinstance("Hello", (float, int, str, list, dict, tuple))

print(x) #Saída: True
```