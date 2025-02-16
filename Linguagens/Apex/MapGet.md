<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [get()](./MapGet.md)

# get()

Para se acessar um valor em um **map** se utiliza o método **get()**. Aqui ao invés de usar o índice como em uma [lista](./List.md), se utiliza o valor da **chave**. Segue o exemplo:

```apex
Map<String, Integer> myMap = new Map<String, Integer>{'Primeiro valor' => 10};

System.debug(myMap.get('Primeiro valor'));
```

Caso a chave passada como argumento uma chave que não exista no **map**, será retornado [null](./Null.md). 