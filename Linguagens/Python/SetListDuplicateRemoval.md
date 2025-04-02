<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Removendo duplicados de uma lista com set](./SetListDuplicateRemoval.md)

# Removendo duplicados de uma lista com set

Uma das maneiras que um [set](./Set.md) é mais utilizado em [Python](./Index.md) é para remover elementos duplicados em uma [lista](./List.md). Basta transformar a lista em um set e depois transformar em lista novamente:

```python
list_duplicados = (1, 2, 2, 3, 3, 4, 5)
list_uniq = list(set(list_duplicados))

print(list_uniq)  # [1, 2, 3, 4, 5]
```