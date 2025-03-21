<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [values()](./DictValues.md)

# values()

O método de [dict](./Dict.md) `values()` funciona de maneira similar ao [`keys()`](./DictKeys.md). Porém, o `values()` retorna os valores de um dicionário. O retorno é um objeto da classe 'dict_values', portando isso gera a particularidade de que se os valores do dicionário original forem alterados, a variável com os valores tbm será modificada:

```python
car = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}

x = car.values()

car["year"] = 2018

print(x) #dict_values(['Ford', 'Mustang', 2018])
```