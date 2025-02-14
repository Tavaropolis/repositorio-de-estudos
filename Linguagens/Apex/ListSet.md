<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [set()](./ListSet.md)

# set()

Para alterar um elemento dentro de uma lista se utiliza o método **set()**. Ele recebe dois argumentos, o primeiro sendo o índice do elemento que se deseja mudar, e o segundo, sendo o novo valor que ele deve receber: 

```apex
List<String> fruits = new List<String>{'Apple', 'Banana', 'Cherry', 'Date'};

fruits.set(1, 'Blueberry'); //Alterou 'Banana' para 'Blueberry'
```
