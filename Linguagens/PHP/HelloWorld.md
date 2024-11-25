<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações PHP](./Index.md) > [Hello World](./HelloWorld.md)

# Hello World

Quando estamos aprendendo uma nova tecnologia é muito comum que a primeira coisa que aprendemos a fazer é exibir uma mensagem na tela.

O **PHP** funcionam em arquivos de extenção **.php**. Ele funciona como um arquivo HTML, todas as tags são interpretadas, é possível importar CSS e [Javascript](../Javascript/Index.md) completamente normalmente.

A principal diferença é que podemos abrir uma tag com **<?php php>**. Tudo que estiver dentro dessa tag, será interpretado como código PHP.

A função para exibir uma mensagem no PHP é o **echo**. Basta utiliza-lo conforme o exemplo abaixo: 

```php
<?php
    echo "Hello World";
?>
```

Como isso é uma ação muito rotineira, o PHP possui um atalho para esses casos onde podemos substituir por: 

```php
<?= "Hello World" ?>
```