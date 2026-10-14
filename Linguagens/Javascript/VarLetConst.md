<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Javascript](./Index.md)

# `var`, `let` e `const` no JavaScript

As três palavras declaram variáveis, mas diferem no **escopo** e na possibilidade de **reatribuir valores**.

## `let`

- Tem **escopo de bloco** (`{ ... }`).
- Permite reatribuir o valor.
- Não permite declarar novamente a mesma variável no mesmo escopo.

```javascript
let idade = 20;
idade = 21; // OK

if (true) {
  let mensagem = "Olá";
}
// console.log(mensagem); // Erro: fora do escopo
```

## `const`

- Tem **escopo de bloco**.
- Não permite reatribuir a variável.
- Precisa receber um valor na declaração.
- Se guardar um objeto ou array, o conteúdo ainda pode ser alterado.

```javascript
const nome = "Ana";
// nome = "Bia"; // Erro

const numeros = [1, 2];
numeros.push(3); // OK
// numeros = [4, 5]; // Erro
```

## `var`

- Tem **escopo de função**, não de bloco.
- Permite reatribuir o valor.
- Permite redeclarar a mesma variável no mesmo escopo.
- Pode ser acessada antes da linha da declaração devido ao *[hoisting](./Hoisting.md)*, mas nesse caso seu valor será `undefined` até a atribuição.

```javascript
if (true) {
  var ativo = true;
}
console.log(ativo); // true

function exemplo() {
  var x = 1;
  var x = 2; // Permitido
}
```

## Resumo

| Característica | `var` | `let` | `const` |
|---|---|---|---|
| Escopo | Função | Bloco | Bloco |
| Pode reatribuir? | Sim | Sim | Não |
| Pode redeclarar no mesmo escopo? | Sim | Não | Não |
| Exige valor inicial? | Não | Não | Sim |

**Regra prática:** prefira `const` por padrão; use `let` quando precisar reatribuir a variável. Evite `var` em código moderno, salvo quando houver um motivo específico.
