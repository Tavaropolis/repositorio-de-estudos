<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Javascript](./Index.md) > [Tipos de dados](./TiposDeDados.md)

# Tipos de Dados

JavaScript possui **7 tipos primitivos** e o tipo `Object`, que representa valores não primitivos. Abaixo está uma lista de referência dos tipos e de algumas categorias importantes:

| Categoria | Tipos |
|---|---|
| Texto | [string](./String.md) |
| Numérico | [number](./Number.md), [bigint](./BigInt.md) |
| Booleano | [boolean](./Boolean.md) |
| Ausência de valor | [undefined](./Undefined.md), [null](./Null.md) |
| Identificador único | [symbol](./Symbol.md) |
| Objetos e estruturas | [object](./Object.md), [array](./Array.md), [function](./Function.md) |

## Tipos primitivos

Os 7 tipos primitivos do JavaScript são:

- `string`: representa textos.
- `number`: representa números inteiros e decimais, além de valores especiais como `NaN` e `Infinity`.
- `bigint`: representa números inteiros de precisão arbitrária.
- `boolean`: representa `true` ou `false`.
- `undefined`: indica um valor não definido.
- `null`: representa intencionalmente a ausência de um valor.
- `symbol`: representa identificadores únicos.

## Objetos

O tipo `object` representa valores não primitivos. Entre eles estão:

- **Objetos literais:** agrupam propriedades e valores.
- **Arrays:** armazenam coleções ordenadas de valores.
- **Funções:** objetos que podem ser chamados para executar código.
- **Outros objetos:** como `Date`, `Map`, `Set` e `RegExp`.

Arrays e funções não são tipos primitivos independentes. São categorias especiais de objetos.

## Verificando tipos com `typeof`

```javascript
typeof "Olá";          // "string"
typeof 42;             // "number"
typeof 10n;            // "bigint"
typeof true;           // "boolean"
typeof undefined;      // "undefined"
typeof Symbol("id");   // "symbol"
typeof {};             // "object"
typeof [];             // "object"
typeof function() {};  // "function"
typeof null;           // "object"
```

## Observações importantes

- JavaScript não separa `int` e `float`: ambos são representados pelo tipo `number`.
- `typeof null` retorna `"object"` por uma particularidade histórica da linguagem. Apesar disso, `null` é um tipo primitivo.
- `typeof` retorna `"function"` para funções, embora elas sejam objetos chamáveis.
- A lista de tipos primitivos é diferente da lista de classes e objetos nativos disponíveis na linguagem.