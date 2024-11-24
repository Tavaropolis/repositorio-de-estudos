<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações PHP](./Index.md) > [Localhost](./Localhost.md)

# Localhost

O PHP é uma linguagem de programação backend, ou seja, a fim de nosso código ser executado precisamos roda-lo em um servidor. 

Podemos utilizar a nossa própria máquina como um servidor local, chamando um IP próprio (127.0.0.1), o **localhost**. Este endereço é utilizado para desenvolvimento apenas.

Pode-se ser utilizado programas como o XAMPP para rodar um servidor local PHP. Porém o PHP atual possui um servidor nativo build-in.

Para executar o localhost basta executar o comando abaixo no terminal. A porta não precisa ser necessáriamente 8000 ficando a cargo do desenvolvedor.

```shell
php -S localhost:8000
```