<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [switch when](./SwitchWhen.md)

# switch when

Assim como linguagens como [C](../C/Index.md) e [Javascript](../Javascript/Index.md), **Apex** também tem seu `switch statement`.

O `switch` é muito útil para quando temos uma gama delimitada de valores. Ao contrário dos [if](./IfElse.md), não podemos criar uma condição que se verdadeira cairá no bloco. No `switch` caso o calor da variável seja o mesmo do when, o bloco será executado. Note que ao contrário de muitas linguagens, em Apex não é necessário utilizar o **break**.

```apex
switch on i {
   when 1 {
       System.debug('when block 1');
   }
   when 2 {
       System.debug('when block 2');
   }
   when 3 {
       System.debug('when block 3');
   }
}
```

Podemos até mesmo atribuir mais de um valor para um **when**:

```apex
switch on i {
   when 2, 3, 4 {
       System.debug('when block 2 and 3 and 4');
   }
   when 5, 6 {
       System.debug('when block 5 and 6');
   }
   when 7 {
       System.debug('when block 7');
   }
   when else {
       System.debug('default');
   }
}
```

Podemos definir um **else** caso a variável avaliada não caía em nenhum dos **when**:

```apex
switch on i {
   when 1 {
       System.debug('when block 1');
   }
   when 2 {
       System.debug('when block 2');
   }
   when 3 {
       System.debug('when block 3');
   }
   when else {
       System.debug('default value');
   }
}
```

Além disso como todo tipo em **Apex** pode ser null, é possível definir o null como uma condição de **when**:

```apex
switch on i {
   when 2 {
       System.debug('when block 2');
   }
   when null {
       System.debug('bad integer');
   }
   when else {
       System.debug('default ' + i);
   }
}
```