<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [get()](./ListGet.md)

# get()

Para acessar um elemento de uma lista se usa o método **get()**, passando o índice do elemento que se deseja acessar.

```apex
List<String> ninjas = new List<String> {'Naruto', 'Sasuke'};

System.debug(ninjas.get(1)); //Irá retornar Sasuke
```