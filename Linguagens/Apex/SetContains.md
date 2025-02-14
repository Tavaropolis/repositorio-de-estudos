<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [contains()](./SetContains.md)

# contains()

**contains()** é um método de **set** que permite verificar se um determinado elemento existe no set. Esse método retorna um [booleano](./Boolean.md), verdadeiro se o elemento existe no set, e falso se ele não existe:

```apex
Set<String> myString = new Set<String>{'a', 'b'};
Boolean result = myString.contains('z');
```