<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Apex](./Index.md) > [Operadores](./Operadores.md)

# Operadores

A linguagem **Apex**, utilizada na plataforma **Salesforce**, possui diversos operadores para realizar [operações matemáticas](#operadores-aritméticos), [lógicas](#operadores-lógicos) e de [comparação](#operadores-de-comparação).

## Operadores Aritméticos
Utilizados para realizar operações matemáticas básicas.

| Operador | Descrição       | Exemplo        |
|----------|---------------|---------------|
| `+`      | Adição        | `a + b`       |
| `-`      | Subtração     | `a - b`       |
| `*`      | Multiplicação | `a * b`       |
| `/`      | Divisão       | `a / b`       |
| `%`      | Módulo (resto da divisão) | `a % b` |

## Operadores de Atribuição
Utilizados para atribuir valores às variáveis.

| Operador | Descrição                           | Exemplo       |
|----------|-----------------------------------|--------------|
| `=`      | Atribuição                        | `a = 10`     |
| `+=`     | Adição e atribuição               | `a += 5`     |
| `-=`     | Subtração e atribuição            | `a -= 3`     |
| `*=`     | Multiplicação e atribuição        | `a *= 2`     |
| `/=`     | Divisão e atribuição              | `a /= 4`     |
| `%=`     | Módulo e atribuição               | `a %= 2`     |

## Operadores de Comparação
Usados para comparar valores e retornar **true** ou **false**.

| Operador | Descrição                         | Exemplo       |
|----------|-----------------------------------|--------------|
| `==`     | Igualdade                         | `a == b`     |
| `!=`     | Diferença                         | `a != b`     |
| `>`      | Maior que                         | `a > b`      |
| `<`      | Menor que                         | `a < b`      |
| `>=`     | Maior ou igual                    | `a >= b`     |
| `<=`     | Menor ou igual                    | `a <= b`     |

## Operadores Lógicos
Usados para combinar expressões booleanas.

| Operador | Descrição                         | Exemplo            |
|----------|-----------------------------------|--------------------|
| `&&`     | E lógico (AND)                    | `a > 10 && b < 5`  |
| `||`     | OU lógico (OR)                    | `a > 10 || b < 5`  |
| `!`      | Negação lógica (NOT)              | `!(a == b)`        |

## Operadores Bitwise
Operam em bits individuais de números inteiros.

| Operador | Descrição                         | Exemplo     |
|----------|-----------------------------------|------------|
| `&`      | AND bit a bit                    | `a & b`    |
| `|`      | OR bit a bit                     | `a | b`    |
| `^`      | XOR bit a bit                    | `a ^ b`    |
| `~`      | Complemento bit a bit (NOT)      | `~a`       |
| `<<`     | Deslocamento à esquerda          | `a << 2`   |
| `>>`     | Deslocamento à direita           | `a >> 2`   |

## Operador Ternário
Uma forma simplificada de escrever **if-else**.

| Operador | Descrição | Exemplo |
|----------|----------|---------|
| `? :`    | Expressão condicional | `resultado = (a > b) ? "Maior" : "Menor";` |

## Operador de Instância
Verifica se um objeto pertence a uma classe específica.

| Operador | Descrição | Exemplo |
|----------|----------|---------|
| `instanceof` | Verifica se um objeto é instância de uma classe | `if (obj instanceof Conta) { ... }` |