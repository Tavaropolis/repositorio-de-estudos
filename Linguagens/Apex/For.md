<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [for](./For.md)

# for

O **`for`**  é um dos três laços de repetição do **Apex** (os outros são o [while](./While.md) e o [do while](./DoWhile.md)).

O `for` é mais recomendado para quando temos um tempo definido de quantas vezes queremos que um código se repita. Em **Apex** a notação é muito parecida com o for clássico do [C](../C/Index.md).

A estrutura é composta em três partes dentro do `()`: 
- A primeira se declara uma variável de controle
- A segunda uma condicional, onde se ela for verdadeira, o laço se repete
- A terceira a incrementação/decrécimo da variável de controle

Tudo que fazemos no **for** também pode ser feito com o while
```apex
for (Integer i = 1; i <= 5; i++) {
    System.debug('Valor de i: ' + i); //Exibirá valores de 1 a 5
}
```

Assim como no **while**, quando existe apenas uma linha de instrução, a delimitação do bloco com `{}` é opcional, e vai rodar sem problemas sem ele: 

```apex
for (Integer num = 1; num <= 3; num++) 
    System.debug('Número: ' + num);
```
Assim como em [Java](../Java/Index.md), o **Apex** possui uma forma alternativa para iterar coleções (e no caso do Apex, [SObjects](./SObjects.md)) com `for`:

- ### Percorrendo Listas
  ```apex
  List<String> nomes = new List<String>{ 'Alice', 'Bob', 'Charlie' };

    for (String nome : nomes) {
        System.debug('Nome: ' + nome);
    }
  ```

- ### Percorrendo Sets
  ```apex
  Set<Integer> numeros = new Set<Integer>{ 10, 20, 30 };

    for (Integer num : numeros) {
        System.debug('Número: ' + num);
    }
  ```

- ### Percorrendo Maps
  ```apex
  Map<Integer, String> idParaNome = new Map<Integer, String>{
    1 => 'Alice',
    2 => 'Bob',
    3 => 'Charlie'
    };

    // Iterando pelas chaves e valores
    for (Integer id : idParaNome.keySet()) {
        System.debug('ID: ' + id + ', Nome: ' + idParaNome.get(id));
    }
  ```

- ### Percorrendo um SObject
    ```apex 
    List<Account> contas = [SELECT Id, Name FROM Account LIMIT 5];

    for (Account acc : contas) {
        System.debug('Conta ID: ' + acc.Id + ', Nome: ' + acc.Name);
    }
    ```
Como todos os loops em **Apex**, é possível utilizar as palavras reservadas: [continue](./Continue.md) e [break](./Break.md).

O **continue** faz pular para a próxima iteração do laço:

```apex
for (Integer i = 1; i <= 5; i++) {
    if (i == 3) continue; // Pula o número 3
    System.debug('Número: ' + i);
}
```

O **break** faz o laço todo ser interrompido:

```apex
for (Integer i = 1; i <= 5; i++) {
    if (i == 3) break; // Para o laço no número 3
    System.debug('Número: ' + i);
}
```