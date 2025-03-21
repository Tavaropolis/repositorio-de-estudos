<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [get()](./DictGet.md)

# get()

Em [Python](./Index.md) é possível resgatar o valor de uma chave de um [dict](./Dict.md) através do método `get()`. Lembrando que é um método de dict, você precisa ter uma variável dict criada para poder utilizar:

```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}

x = thisdict.get("model")  #Saída Mustang
```

O `get()` ainda aceita um segundo argumento, que é o que será devolvido caso a chave não exista:
```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}

x = thisdict.get("owner", "João Silva")  #Saída João Silva
```