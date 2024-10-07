<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Linux CLI](./Index.md) > [Variáveis](./Variaveis.md)

# Variáveis

O Shell do Linux nos permite a criação de variáveis, igual uma linguagem comum de programação. Para atribuir uma variável utilizamos o sinal de **=**. Importante notar que não pode haver espaços entre o nome da variável o sinal de =, se houver o Shell vai identificar como um parametro de um programa. 

Por convenção é comum que os nomes dad variáveis sejam inteiramente em maiúsculo, porém não é uma regra.

```shell
nome='Gabriel'
```

Para manipular e utilizar a variável é preciso utilizar o **$** antes do nome da variável.

```shell
echo $nome
```

## Variáveis pré-estabelecidas
O Linux já possuí algumas variáveis pré-estabelecidas e da pra usar elas em aplicações por exemplo.

- **$USER**
  
  Retorna o usuário em atividade no Linux.
  ```shell
  echo $USER
  ```

- **$HOME**
  
  Retorna qual é o diretório home do usuário em execução.
  ```shell
  echo $HOME
  ```