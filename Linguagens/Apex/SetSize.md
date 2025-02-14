<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [size()](./SetSize.md)

# size()

O **size()** do Set funciona da mesma maneira que o de [lista](./ListSize.md), devolvendo o número de lementos dentro de um **set**.

```apex
Set<String> ninjas = new Set<String>{'Naruto', 'Sasuke', 'Sakura'};

System.debug(ninjas.size()); //Irá retornar 3
```