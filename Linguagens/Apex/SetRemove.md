<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [remove()](./SetRemove.md)

# remove()

**remove()** é um método de set que remove um elemento com base no **valor** desse elemento (já que sets não possuem índices).

```apex
Set<Integer> numbers = new Set<Integer>{1, 2, 3, 4, 5};
numbers.clear(2); //Removeu o elemento de valor 2
```