<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [add()](./ListAdd.md)

# add()

A maneira mais fácil de se adicionar items em uma lista é através do método de lista **add()**. Esse método irá adicionar um novo elemento no índice final da lista.

```apex
List<String> ninjas = new List<String> {'Naruto', 'Sasuke'};

ninjas.add('Sakura');
```

É possível usar o **add()** para adicionar o elemento dentro de um índice específico, passando dois argumentos, o primeiro sendo o índice e o segundo, o elemento que se deseja adicionar.

```apex
List<Integer> myList = new Integer[6];

myList.add(0, 47);
myList.add(1, 52);
```