<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Linux CLI](./Index.md) > [Pattern Match](./PatternMatch.md)

# Pattern Match

Quando trabalhamos com arquivos e pastas no Linux, o Shell nos permite uma técnica **(Pattern Match)** para a passagem de argumentos através de caracteres coringas. Segue os principais caracteres coringas:

## **\***

O Shell substitui o coringa **\*** por uma sring. Por exemplo, vamos supor que eu queira listar todos os arquivos com a extensão .txt, bastaria fazer o seguinte comando:

```shell
ls *.txt
```

## **?**
O Shell substitui o **?** por qualquer caractere (ao contrario do \* que virava uma string inteira). Supondo que eu tenha arquivos chamadas "Capitulo1.txt", "Capitulo2.txt" e "Capitulo3.txt". Posso usar o **grep** para procurar uma palavra (nesse caso, a palavra Linux) nesses arquivos.

```shell
grep Linux Capitulo?.txt
```

Se eu quisesse selecionar do Capitulo10 ao 99 bastaria fazer.

```shell
grep Linux Capitulo??.txt
```

## **[]**

Os colchetes são menos usuais, mas serve para especificar alguns carateres específios ou uma sequência. Por exemplo, se eu quisesse só os capitulos pares de 0 a 9, seria assim.: 

```shell
ls Capitulo[02468].txt
```

Ou utilizando uma sequência

```shell
ls Capitulo[0-9].txt
```