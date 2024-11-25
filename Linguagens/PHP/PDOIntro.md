<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações PHP](./Index.md) > [Habilitando o PDO](./PDOIntro.md)

# Habilitando o PDO
**PDO** (PHP Data Object) é uma das das duas formas de realizar a conexão entre o PHP e o um banco de dados SQL. 

Para habilitar o PDO é necessário entrar na pasta de instalação do PHP, e modificar o arquivo php.ini. É necessário descomentar as seguintes linhas:

## No Windows
```txt
extension=php_pdo.dll
extension=php_pdo_mysql.dll
```

## No Linux
```
extension=pdo.so
extension=pdo_mysql.so
```