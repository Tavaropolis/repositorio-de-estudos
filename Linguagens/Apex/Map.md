<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Map](./Map.md)

# Map

**Map** é o terceiro e último tipo de coleção do **Apex**. Um Map é composto por uma estrutura de **chave** e **valor**. Cada chave deve ser um valor único (não podendo repetir), porém os valores podem ser valores repetidos.

Em **Apex** se declara um **map** vazio da seguinte forma (note que tem de se definir o tipo primitivo das chaves e dos valores):

```apex
Map<String, Integer> myMap = new Map<String, Integer>();
```

Para se declarar um **map** já com valores iniciados: 
```apex
Map<String, Integer> myMap = new Map<String, Integer>{'Primeiro valor' => 10};
System.debug(myMap);
``` 