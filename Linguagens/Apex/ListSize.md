<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [size()](./ListSize.md)

# size()

**size()** é um método de lista que retorna o número de elementos presentes nela. Segue exemplo: 

```apex
List<String> ninjas = new List<String>{'Naruto', 'Sasuke', 'Sakura'};

System.debug(ninjas.size()); //Irá retornar 3
```