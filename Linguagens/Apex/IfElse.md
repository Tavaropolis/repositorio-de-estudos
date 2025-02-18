<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [if / else](./IfElse.md)

# if / else

Durante a execução do nosso script é comum querermos manipular o fluxo de execução, ou que certas coisas só aconteçam em determinadas situações, é para isso que serve a estrutura **`if / else`**.

O **if / else** funciona da seguinte maneira: o **Apex** avaliará a condição do if, e se verdadeiro, executará o código de dentro do if, caso seja falso, executará o else. Lembrando que a presença do else é opcional. Segue exemplo:

```apex
if (idade >= 18) {
    System.debug('Você é maior de idade.');
} else {
    System.debug('Você é menor de idade.');
}
```

Podemos utilizar mais de uma condição no **if** utilizando um **`else if`**. Por exemplo: 

```apex
if (nota >= 90) {
    System.debug('Excelente!');
} else if (nota >= 70) {
    System.debug('Bom!');
} else if (nota >= 50) {
    System.debug('Regular.');
} else {
    System.debug('Reprovado.');
}
```