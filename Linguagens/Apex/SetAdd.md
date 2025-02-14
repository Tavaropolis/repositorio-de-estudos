<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [add()](./SetAdd.md)

# add()

Para se adicionar um elemento a um **set**, pode se utilizar o método **add()**. Segue o exemplo:

```apex
Set<Integer> numbers = new Set<Integer>{1, 2, 3};
numbers.add(4);
```

No caso específico de **set**, o **add()** retorna um [booleano](./Boolean.md), sendo true caso o set tenha sido alterado (ou seja, não havia o valor anteriormente no set) e false caso não tenha sido alterado:

```apex
Set<String> myString = new Set<String>{'a', 'b', 'c'};
Boolean result = myString.add('d');

System.debug(result); //Irá exibir true
```