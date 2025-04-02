<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Shallow Copy e Deep Copy](./ShallowCopyDeepCopy.md)

# Shallow Copy e Deep Copy

O [Python](./Index.md) trabalha com referência de memória quando utilizamos tipos mutáveis ([listas](./List.md) e [dicionários](./Dict.md)). Vou exemplificar com o código abaixo. Aqui **d2** não sim recebendo o valor de **d1**, mas sim a referência da memória onde essa lista está salva. Qualquer alteração em uma das variáveis vai refletir na outra. 

```python
d1 = {
    'c1': 1,
    'c2': 2,
    'l1': [0, 1, 2]
}

d2 = d1

d2['c1'] = 1000
d2['l1'][1] = 999999

print(d1)
```

Para resolver essa situação é necessário criar uma cópia da lista. Podemos criar uma cópia com o método `copy()`. Por padrão o `copy()` gera um `shallow copy`, isso significa que todos os tipos imutáveis dentro da lista são copiados, porém todas as listas e dicionários dentro do objeto copiado, ainda compartilham referências de memória.

```python
d1 = {
    'c1': 1,
    'c2': 2,
    'l1': [0, 1, 2]
}

d2 = d1.copy()

d2['c1'] = 1000
d2['l1'][1] = 999999

print(d1)
print(d2)
```

Também é possível criar uma shallow copy com o `módulo copy`:

```python
import copy

d1 = {
    'c1': 1,
    'c2': 2,
    'l1': [0, 1, 2]
}

d2 = copy.copy(d1) #Criando um shallow copy

d2['c1'] = 1000
d2['l1'][1] = 999999

print(d1) #d1 também foi alterado por ser uma shallow copy
print(d2)
```

Para resolvermos essa situação podemos criar uma `deep copy`, onde todos os dados serão copiados, porém ocupando mais memória:

```python
import copy

d1 = {
    'c1': 1,
    'c2': 2,
    'l1': [0, 1, 2]
}

d2 = copy.deepcopy(d1) #Criando um shallow copy

d2['c1'] = 1000
d2['l1'][1] = 999999

print(d1) #d1 não foi alterado por ser uma deep copy
```