<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [break](./Break.md)

# break

O **`break`** é uma palavra reservada do [Apex](./Apex.md) usanda em laços de repetição (assim como o [continue](./Continue.md)). Quando o código chega no **`break`**, o laço de repetição é imediatamente interrompido.

- ### Break em um while
  ```apex
    Integer j = 1;

    while (true) { // Loop infinito
        System.debug('Valor de j: ' + j);
        if (j == 4) break; // Sai do loop quando j == 4
        j++;
    }
  ```

- ### Break em um do while
  ```apex
    Integer j = 1;

    do {
        System.debug('Valor de j: ' + j);
        if (j == 4) break; // Sai do loop quando j == 4
        j++;
    } while (true); // Loop infinito
  ```

- ### Break em um for
    ```apex
    for (Integer i = 1; i <= 5; i++) {
        if (i == 3) break; // Para o laço no número 3
        System.debug('Número: ' + i);
    }
    ```