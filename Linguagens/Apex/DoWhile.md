<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [do while](./DoWhile.md)

# do while

O **`do while`**  é um dos três laços de repetição do **Apex** (os outros são o [while](./While.md) e o [for](./For.md)).

Ele funciona de maneira muito similar ao ao **while**, onde o interpretador Apex vai analisar uma condição e caso ela seja verdadeira o bloco será executado novamente. A diferença está que no **`do while`** a avaliação da condição só ocorre no final do bloco, ou seja, você tem a garantia que o bloco será executado uma vez, mesmo que a condição seja falsa.

```apex
Integer contador = 1;

do {
    System.debug('Contador: ' + contador);
    contador++;
} while (contador <= 5);
```

Assim como no **while**, quando existe apenas uma linha de instrução, a delimitação do bloco com `{}` é opcional, e vai rodar sem problemas sem ele: 

```apex
Integer num = 1;

do 
    System.debug('Número: ' + num++);
while (num <= 3);
```

Como todos os loops em **Apex**, é possível utilizar as palavras reservadas: [continue](./Continue.md) e [break](./Break.md).

O **continue** faz pular para a próxima iteração do laço:

```apex
Integer i = 0;

do {
    i++;
    if (i == 3) continue; // Pula o número 3
    System.debug('Número: ' + i);
} while (i < 5);
```

O **break** faz o laço todo ser interrompido:

```apex
Integer j = 1;

do {
    System.debug('Valor de j: ' + j);
    if (j == 4) break; // Sai do loop quando j == 4
    j++;
} while (true); // Loop infinito

```