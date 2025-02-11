<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Long](./Long.md)

# Long

Long é um tipo de dado primitivo que assim como [Integer](./Integer.md) guarda um valor de número inteiro. A diferença entre os dois tipos é que o **Long** pode armazenar uma faixa maior de valores (entre -2^63 até (2^63) - 1), porém ocupando um espaço maior na memória.

Para Declarar um long, segue-se a seguinte síntaxe: 
```apex
Long l = 2147483648;
```

Ou também é possível usar uma síntaxe alternativa com um **L** no final: 
```apex
Long l = 2147483648L;
```

## Convesão Long para String

Para converter um dado do tipo Long em uma [String](./String.md) basta utilizar o método de Long chamado [format()](./LongFormat.md).

```apex
Long myLong = 4271990;
String myString = myLong.format();
```

## Conversão Long para Integer

Para converter um dado tipo **Long** em [Integer](./Integer.md), podemos utilizar o método [intValue()](./LongIntValue.md):

```apex
Long myLong = 7191991;
Integer value = myLong.intValue();
```

## Conversão de String para Long

Para transformar uma String em Long basta utilizar o método **[valueOf()](./LongValueOf.md)**. Note que esse é um método estático, você não precisa instanciar um objeto para invocá-lo.

```apex
Long L1 = long.valueOf('123456789');
```