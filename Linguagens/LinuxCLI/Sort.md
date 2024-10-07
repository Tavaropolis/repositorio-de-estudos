<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Linux CLI](./Index.md) > [Sort](./Sort.md)

# Sort

Sorte é um comando que nos permite ordenadar um conjunto de dados de maneira crescente ou decrescente, podendo ser tanto texto quanto númericos.

```shell
sort nomedoarquivo.txt
```

## Flags
- **-r**

    Por padrão o sorte organiza os dados de maneira crescente, para especificar que desejamos decrescente temos de passar a flag -r.

    ```shell
    sort -r nomedoarquivo.txt
    ```
- **-n**
   
    Por padrão o sort organiza textos, mas podemos especificar que queremos organizar números com a flag **-n**.

    ```shell
    sort -n nomedoarquivo.txt
    ```