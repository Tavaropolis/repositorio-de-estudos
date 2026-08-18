<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [HEAD e Referências de Commits](./Head.md)

- [HEAD](#head)
- [HEAD~](#head-1)
- [HEAD^](#head-2)
- [Hash do commit](#head-e-referências-de-commits)

# HEAD e Referências de Commits

O Git possui algumas nomenclaturas especiais para se referir a commits sem precisar escrever seus hashes completos.

## Head
HEAD representa o commit em que você está atualmente. Por exemplo:

A ─── B ─── C
          ▲
         HEAD

Aqui:

```bash
git show HEAD
```

mostra o commit C.

Em uma branch, normalmente o HEAD aponta para o commit mais recente daquela branch.

## HEAD~
`~` significa "voltar pelos primeiros pais do commit".

Assim, `HEAD~1`, ou simplesmente, `HEAD~`, significa o commit imediatamente anterior ao HEAD.

Exemplo:

A ─── B ─── C
          ▲
         HEAD

Então:

- `HEAD`    = C
- `HEAD~1`  = B
- `HEAD~2`  = A

Podemos usar isso em comandos:

```bash
git show HEAD~1
```

ou:

```bash
git restore --source=HEAD~1 arquivo.txt
```

## HEAD^
`^` também pode significar o pai imediato de um commit.

Em um histórico simples:

A ─── B ─── C
          ▲
         HEAD

temos:

- `HEAD`   = C
- `HEAD^`  = B
- `HEAD^^` = A

Para históricos lineares:

- `HEAD~1` == `HEAD^`
- `HEAD~2` == `HEAD^^`

## Hash do commit
Todo commit possui um identificador, normalmente apresentado como um hash:

a8f3c92e7b1...

Podemos usá-lo diretamente:

```bash
git show a8f3c92
```

Geralmente não precisamos escrever o hash inteiro. Uma parte suficientemente única costuma ser suficiente:

```bash
git show a8f3c92
```

## @
`@` é uma abreviação para `HEAD`.

Portanto:

```bash
git show @
```

é equivalente a:

```bash
git show HEAD
```

Também podemos combinar:

- `@~1`
- `@~2`
- `@^`

Por exemplo:

```bash
git show @~2
```

é equivalente a:

```bash
git show HEAD~2
```