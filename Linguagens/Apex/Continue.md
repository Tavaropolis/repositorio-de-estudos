<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [continue](./Continue.md)

# continue

O **`continue`** é uma das palavras reservadas do [Apex](./Index.md). Ela serve para ser utilizada dentro de  um laço de repetição ([while](./While.md), [do while](./DoWhile.md) ou [for](./For.md)). Uma vez que o **`continue`** acionado, o programa pula aquela iteração e parte para a próxima. 

- ### Continue em um while
    ```apex
    Integer i = 0;

    while (i < 5) {
        i++;
        if (i == 3) continue; // Pula o número 3
        System.debug('Número: ' + i);
    }
    ```     

- ### Continue em um do while
    ```apex
    Integer i = 0;

    do {
        i++;
        if (i == 3) continue; // Pula o número 3
        System.debug('Número: ' + i);
    } while (i < 5);
    ```

- ### Continue em um for
    ```apex
    for (Integer i = 1; i <= 5; i++) {
        if (i == 3) continue; // Pula o número 3
        System.debug('Número: ' + i);
    }
    ``` 