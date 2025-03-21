<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [keys()](./DictKeys.md)

# keys()

`keys()` é um método de [dict](./Dict.md). Ele retorna todas as chaves presentes em um dicionário. As chaves são retornadas como um objeto da classe `dict_keys`, o que causa a particularidade de que se o dicionário original for modificado, sua variável com as chaves também serão alteradas:

```python
car = {
"brand": "Ford",
"model": "Mustang",
"year": 1964
}

x = car.keys()

print(x) #dict_keys(['brand', 'model', 'year'])

car["color"] = "white"

print(x) #dict_keys(['brand', 'model', 'year', 'color'])
```



