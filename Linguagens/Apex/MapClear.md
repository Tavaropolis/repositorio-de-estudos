<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [clear()](./MapClear.md)

# clear()

Esse método funciona da mesma maneira que os de [lista](./ListClear.md) e o de [set](./SetClear.md), limpando todos os valores de um **map** o deixando completamente vazio.

```apex
Map<String, String> colorCodes = new Map<String, String>();

colorCodes.put('Red', 'FF0000');
colorCodes.put('Blue', '0000A0');

colorCodes.clear()
```