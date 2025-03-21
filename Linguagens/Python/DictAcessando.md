<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Acessando o Dict](./DictAcessando.md)

# Acessando o Dict

Para acessar o valor de um [Dict](./Dict.md), o método mais comum é chamando a chave através de um `[]`. Isso irá retornar o valor correspondente aquela chave:

```python
thisdict = {
  "brand": "Ford",
  "model": "Mustang",
  "year": 1964
}

x = thisdict["model"] #Saída Mustang
```

Além disso, também é possível resgatar o valor através do método [`get()`](./DictGet.md)
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