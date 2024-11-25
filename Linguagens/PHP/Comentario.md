<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações PHP](./Index.md) > [Comentários](./Comentario.md)

# Comentários

Comentários são linhas no código que não serão executadas, elas servem para fins de documentação e deixar outros programadores cientes do que está acontecendo no código.

No **PHP** existem três formas de se definir um comentário:

A primeira é através de **//**
```php
<?php 
    //Isto é um comentário
    echo "Hello World";
?>
```

A segunda é através de **#**
```php
<?php
    #Isto é um comentário
    echo "Hello World";
?>
``` 

A terceira é através do **/\* \*/**. Neste caso, é possível fazer um comentário de múltiplas linhas.

```php
<?php
    /*
    Este comentário
    tem múltiplas linhas
    */

    echo "Hello World";

?>
```