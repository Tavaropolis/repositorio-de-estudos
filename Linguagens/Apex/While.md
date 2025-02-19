<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [while](./While.md)

# while

**`While`** é uma das estruturas mais comuns da programação e é um dos três laços de repetição do **Apex** (os outros são o [do while](./DoWhile.md) e o [for](./For.md)).

O **while** consiste em um bloco de código que é executado caso a condição do **while** seja verdadeira. Uma vez que todo o código de dentro do bloco é executado, é verificado de a condição **while** ainda é verdadeira, e caso seja, o código é executado novamente.

```apex
Integer count = 1;

while (count < 11) {
    System.debug(count);
    count++;
}
```

Se houver apenas uma linha de instrução dentro do **while**, é opcional delimitar o bloco com ``{}` ou não. Por exemplo:

```apex
Integer num = 1;

while (num <= 3) 
    System.debug('Número: ' + num++);
```

Como todos os loops em **Apex**, é possível utilizar as palavras reservadas: [continue](./Continue.md) e [break](./Break.md).

O **continue** faz pular para a próxima iteração do laço:

```apex
Integer i = 0;

while (i < 5) {
    i++;
    if (i == 3) continue; // Pula o número 3
    System.debug('Número: ' + i);
}
```

O **break** faz o laço todo ser interrompido:

```apex
Integer j = 1;
while (true) { // Loop infinito
    System.debug('Valor de j: ' + j);
    if (j == 4) break; // Sai do loop quando j == 4
    j++;
}
```