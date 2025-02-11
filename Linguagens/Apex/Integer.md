<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Integer](./Integer.md)

# Integer

Integer é o tipo de dado referente aos números inteiros que estejam entre o intevalo de - 2,147,483,648 até 2,147,483,647.

Para declarar um **Integer** em **Apex**, seguimos a seguinte notação:

```apex
    Integer idade = 30; // Tipo inteiro
```

## Conversão Integer para String

Para converter um Integer em [String](./String.md) podemos utilizar o método de Integer chamado **[format()](./IntegerFormat.md)**.

```apex
Integer varInt = 9;
String varString = varInt.format();

System.debug(varString);
```

## Conversão de String para Integer

Para fazer o sentido inverso, transformar uma String em Integer podemos utilizar o método **[valueOf()](./IntegerValueOf.md)**.

```apex
Integer myInt = Integer.valueOf('123');
```