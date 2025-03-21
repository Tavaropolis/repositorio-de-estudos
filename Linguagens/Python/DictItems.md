<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [values()](./DictValues.md)

# items()

É um método de [dict](./Dict.md) funciona de maneira similar aos métodos `keys()` e `values()`. Aqui ele retorna o conjunto de chave e valor dentro de uma [tupla](./Tuple.md). O retorno do `items()` é um objeto do tipo dict_items, portanto cada mudança no dicionário original, vai causar alterações na variável de items.

```python
car = {
"brand": "Ford",
"model": "Mustang",
"year": 1964
}

x = car.items()

print(x) #dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])

car["year"] = 2020

print(x) #dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 2020)])
```