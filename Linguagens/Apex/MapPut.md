<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [put()](./MapPut.md)

# put()

 A forma mais comum de se adicionar um novo elemento a um **map** é através do método **put()**. Esse método recebe dois argumentos, o primeiro é a chave (que deve ser única no map), e o segundo argumento é o valor que se deseja adicionar:
 
```apex
Map<String, Integer> myMap = new Map<String, Integer>{'Primeiro valor' => 10};

myMap.put('Segundo Valor', 20);

System.debug(myMap);
```

**put()** também pode ser utilizado para alterar um valor já presente no map, basta passar uma chave que já exista e um novo valor:

```apex
Map<String, Integer> myMap = new Map<String, Integer>{'Primeiro valor' => 10};

myMap.put('Primeiro Valor', 20);
```