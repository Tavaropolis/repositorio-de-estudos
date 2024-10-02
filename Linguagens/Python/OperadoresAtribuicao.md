<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Operadores de Atribuição](./OperadoresAtribuicao.md)

# Operadores de atribuição

| Operador | Ação no código |
|---|---|
| += 2 | x = x + 2 |
| -= 2 | x = x - 2 |
| *= 2 | x = x * 2 |
| /= 2 | x = x / 2 |
| %= 2 | x = x % 2 |
| //= 2 | x = x // 2 |

Além de definir valores para uma variável, é muito comum querermos fazer operações com ele ou altera-la ao longo do código. Para adicionar 1 a x, o código seria assim:

```python
x: int = 1
x = x + 1
```

Como isso é algo muito comum na programação existem os operadores de atribuição, que servem como um atalho para facilitar a escrita desses casos. Você pode ver os principais casos na tabela no início da página.

```python
x: int = 1
x += 1
```