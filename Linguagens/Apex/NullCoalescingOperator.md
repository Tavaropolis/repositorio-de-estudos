<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Null Coalescing Operator](./NullCoalescingOperator.md)

# Null Coalescing Operator

O **`Null Coalescing Operator`** é um operador de **Apex** que nos permite atribuir umm valor caso a variavél observada a esquerda seja null. Bem parecido com a lógica do Coalesce do SQL. Segue o exemplo: 

```apex
    // Caso 1: A variável NÃO é null
    String nomeCliente1 = 'João';
    String nomeFinal1 = nomeCliente1 ?? 'Nome Padrão';
    System.debug('Nome do Cliente 1: ' + nomeFinal1); // Saída esperada: "João"

    // Caso 2: A variável é null
    String nomeCliente2 = null;
    String nomeFinal2 = nomeCliente2 ?? 'Nome Padrão';
    System.debug('Nome do Cliente 2: ' + nomeFinal2); // Saída esperada: "Nome Padrão"
```