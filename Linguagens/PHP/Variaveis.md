<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações PHP](./Index.md) > [Variáveis](./Variaveis.md)

# Variáveis

Variáveis são um dos conceitos mais básicos da programação, o programador aloca um espaço da memória para salvar um dado, que posteriormente pode ser utilizado para fazer outras operações ou ser substituido por outro dado.

Segue a sintaxe de como se declarar uma variável em PHP, note a peculiaridade das variáveis em PHP se iniciam com **$**.

```php
<?php
    $variavel = 5;
?>
```

Agora alguns pontos a se notar alguns pontos em relação a natureza das variáveis do PHP, pois elas fazem o Python ser classificado como uma linguagem **fracamente tipada** e **dinâmica**. 

- **Fracamente tipada** : Significa que ao contrário de linguagens fortemente tipadas como C e Java, em PHP não precisamos dizer que tipo de dado a variável receberá (não se preocupe, vou falar mais sobre tipos mais tarde).
- **Dinâmica**: Significa que a variável é definida em tempo de execução e não em tempo de compilação, ou seja, uma mesma variável pode receber tipos diferentes de dados.

    ```php
    <?php
        $variavel = 10;  // tipo inteiro
        $variavel = "Texto";  // agora é uma string
    ?>
    ```
## Regras de nome de variáveis
Existem algumas regras que se deve seguir na hora de se nomear uma variável no PHP:

- O nome da variável deve começar com **$**.
- O nome deve começar com uma **letra** ou **_**. 
- O nome não pode começar com um número.
- O nome da variável é **case-sensitive**, ou seja, tem diferença entre letras maiúsculas e minúsculas.