 <link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [JavaScript](./Index.md) > [typeof](./Typeof.md)

# typeof

O operador `typeof` permite identificar o tipo de um valor em JavaScript. Ele retorna uma string com o nome do tipo identificado.

## Sintaxe

```javascript
typeof valor;
typeof(valor);
```

Os dois formatos são válidos.

## Exemplos

### Tipos primitivos

```javascript
typeof "Olá";        // "string"
typeof 42;           // "number"
typeof 10n;          // "bigint"
typeof true;         // "boolean"
typeof undefined;    // "undefined"
typeof Symbol("id"); // "symbol"
```

### Objetos e funções

```javascript
typeof {};                // "object"
typeof [];                // "object"
typeof new Date();        // "object"
typeof function() {};     // "function"
```

Arrays e datas são objetos. Funções também são objetos, mas `typeof` retorna `"function"` para elas.

## Casos especiais

### `null`

```javascript
typeof null; // "object"
```

Embora o resultado seja `"object"`, `null` é um tipo primitivo. Esse comportamento é uma particularidade histórica do JavaScript.

### Variáveis não declaradas

```javascript
typeof variavelInexistente; // "undefined"
```

O `typeof` pode ser usado com um identificador que não foi declarado sem lançar um `ReferenceError`. Isso não significa que a variável exista.

Por outro lado, acessar diretamente essa variável causa um erro:

```javascript
// console.log(variavelInexistente);
// ReferenceError
```

### Variáveis declaradas, mas ainda não inicializadas

```javascript
let nome;

// O valor atual é undefined
console.log(typeof nome); // "undefined"
```

Atenção: acessar uma variável declarada com `let` ou `const` antes de sua inicialização pode causar um `ReferenceError`.

## Tabela de referência

| Valor | Resultado |
|---|---|
| `"texto"` | `"string"` |
| `123` | `"number"` |
| `123n` | `"bigint"` |
| `true` / `false` | `"boolean"` |
| `undefined` | `"undefined"` |
| `Symbol()` | `"symbol"` |
| `null` | `"object"` |
| `{}` | `"object"` |
| `[]` | `"object"` |
| `function() {}` | `"function"` |

## Quando utilizar?

O `typeof` é útil quando precisamos verificar o tipo de um valor antes de realizar uma operação.

```javascript
function exibirNome(nome) {
    if (typeof nome === "string") {
        console.log(nome);
    } else {
        console.log("O valor precisa ser um texto.");
    }
}

exibirNome("Ana"); // Ana
exibirNome(123);   // O valor precisa ser um texto.
```

**Observação:** para verificar se um valor é um array, utilize `Array.isArray()` em vez de `typeof`.

```javascript
Array.isArray([1, 2, 3]); // true
Array.isArray({});        // false
```

## Resumo

- `typeof` retorna uma string indicando o tipo de um valor.
- Arrays retornam `"object"`, não `"array"`.
- `typeof null` retorna `"object"` por razões históricas.
- Funções retornam `"function"`.
- Para verificar arrays, utilize `Array.isArray()`.