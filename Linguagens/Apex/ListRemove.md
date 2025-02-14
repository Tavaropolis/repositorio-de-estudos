<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [remove()](./ListRemove.md)

# remove()

O método **remove()** remove um elemento de um índice passado como argumento. Importante notar que os índices são realinhados quando um elemento é removido. Por exemplo, se você retirar o elemento da posição 0, o elemento que estava na posição 1 passa a ser o 0.

```apex
List<Integer> numbers = new List<Integer>{10, 20, 30, 40, 50};
Integer removedElement = numbers.remove(2); 
```