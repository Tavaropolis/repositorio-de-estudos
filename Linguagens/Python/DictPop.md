<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [pop()](./DictPop.md)

# pop()

`pop()` é um método de [dict](./Dict.md) onde você pode passar uma chave como argumento, e ela será removida do dicionário. É importante que a chave exista dentro do dict, se ela não existir, irá ser gerado um erro.

```python
thisdict =	{
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}

thisdict.pop("model")
print(thisdict) #{'brand': 'Ford', 'year': 1964}
```