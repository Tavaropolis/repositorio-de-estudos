<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Linux CLI](./Index.md) > [Head](./Head.md)

# Head
Head é um comando utilizado para ler o início de um arquivo, basicamente uma versão reduzida e mais rápida do **cat**. É possivel utilizar a flag -n para específicar o número de linhas, se a flag não for declarada, o comando exibe as primeiras 10 linhas. 

O comando abaixo exibe as primeiras 3 linhas de um arquivo .txt.

```shell
head -n3 arquivo.txt
```