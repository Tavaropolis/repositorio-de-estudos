<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Set](./Set.md)

# Set

**Set** é outro tipo de coleção presente no **Apex**. As principais diferenças entre um **set** e uma **[lista](./List.md)** é que em um set não é possível adicionar dados repetidos. Além disso em um set os elementos não possuem índices.

Segue exemplo de como definir um set em Apex:

```apex
Set<String> s1 = new Set<String>();
```

Para iniciar um set já com valores:

```apex
Set<Integer> numbers = new Set<Integer>{1, 2, 3};
```

Quando se tenta adicionar dois valores iguais em um **set** não é gerado um erro, porém apenas um dos valores é adicionado.

```apex
Set<Integer> numbers = new Set<Integer>{1, 2, 3};
numbers.add(4);
numbers.add(4);
System.debug(numbers); //Exibirá {1, 2, 3, 4}
```

Uma forma muito utilizada com o **set** é para retirar valores repetidos de uma lista:

```apex
List<String> ninjas = new List<String>{'Naruto', 'Naruto', 'Sasuke', 'Sakura'};

Set<String> setNinjas = new Set<String>(ninjas);

System.debug(setNinjas);  //Todos os valores repetidos foram removidos
```

Diferentemente do [Java](../Java/Index.md) o desenvolvedor não precisa específicar o algoritmo utilizado na criação do **set** (HashSet ou TreeSet por exemplo). Em **Apex** todos os sets são tecnicamente um **HashMap**.