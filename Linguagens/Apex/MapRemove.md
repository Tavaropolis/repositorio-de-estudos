<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [remove()](./MapRemove.md)

# remove()

**remove()** é um método de **map** que permite remover um elemento com base em uma chave passada como argumento:

```apex
Map<String, String> colorCodes = new Map<String, String>();

colorCodes.put('Red', 'FF0000');
colorCodes.put('Blue', '0000A0');

colorCodes.remove('Blue');
```