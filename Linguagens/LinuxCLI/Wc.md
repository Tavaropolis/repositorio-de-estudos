<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Linux CLI](./Index.md) > [WC](./Wc.md)

# Wc

O comando **wc**, abreviado de word counting, faz exatamente essa função: conta o número de linhas, palavras e caracteres de um arquivo. 

```shell
wc nomedoarquivo.txt
```

O retorno seria algo do tipo:
```shell
100 470 3139 nomedoarquivo.txt
```
O primeiro número é o número de linhas, o segundo o número de palavras e o terceiro o número de caracteres.


## Flags
- **-l**
 
    Para especificar que se deseja apenas o números de linhas.
    ```shell
    wc -l arquivo.txt
    ```

- **-w**
  
    Para especificar que se deseja apenas o números de palavras.
    ```shell
    wc -w arquivo.txt
    ```

- **-c**

    Para especificar que se deseja apenas o números de caracteres.
    ```shell
    wc -c arquivo.txt
    ```