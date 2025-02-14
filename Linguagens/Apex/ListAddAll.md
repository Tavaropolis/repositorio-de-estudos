<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [addAll()](./ListAddAll.md)

# addAll()

**addAll()** é um método de lista que permite adicionar todos os elementos de uma segunda lista ou de um [set](./Set.md). Para que o método funcione é preciso que as duas listas sejam do mesmo tipo.

```apex
List<String> names = new List<String>{'Alice', 'Bob'};
List<String> moreNames = new List<String>{'David', 'Eve'};
names.addAll(moreNames);
```