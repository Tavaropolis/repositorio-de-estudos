<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Desempacotamento de Dict](./DictUnpack.md)

# Desempacotamento de Dict

Assim como as [tuplas](./Tuple.md) é possível fazer o desempacotamento em [dicionários](./Dict.md) no [python](./Index.md). Ou seja, podemos distrinchar um dict e atribuir suas partes a variáveis. 

Uma das formas mais comuns de se utilizar o desempacotamente de dicionários no python é com [atribuições múltiplas](./AtribuicaoMultipla.md) e os métodos [`keys()`](./DictKeys.md) e/ou [`values()`](./DictValues.md).

```python
dict1 = {"nome": "Gabriel", "profissao": "Programador"}

a, b = dict1.keys()
c, d = dict1.values()

print(a) #Saída: "nome"
print(b) #Saída: "profissao"   
print(c) #Saída: "Gabriel"
print(d) #Saída: "Programador"
```

Outra função útil do desempacotamento de dicionários no python é para juntar dois ou mais dicionários em um. Para isso basta usar o `**`. Funciona de maneira bem similar ao [Spread Operator](../Javascript/SpreadOperator.md) do [Javascript](../Javascript/Index.md).

```python
dict1 = {"a": 1, "b": 2}
dict2 = {"c": 3, "d": 4}

dict3 = {**dict1, **dict2}
print(dict3) #Saída: {'a': 1, 'b': 2, 'c': 3, 'd': 4}
```