<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Javascript](./Index.md) > [IIFE](./IIFE.md)

# IIFE

O fluxo mais comum de uma função seria declarar a função e depois executá-las através de chamadas. Porém o **Javascript** possuí um recurso onde uma função se executa imediatamente após ser definida. Essas funções são as chamadas **IIFE (*Immediately Invoked Function Expression*)**.

Segue abaixo como definir uma **IIFE**:

```javascript
(function () {
  console.log('Função executada automaticamente!');
})();
```

Pode até se simplificar a síntaxe e utilizar uma **[Arrow function](./ArrowFunction)**.

```javascript
(() => {
  console.log('IIFE com arrow function!');
})();

```