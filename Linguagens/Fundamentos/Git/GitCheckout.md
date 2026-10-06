<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git checkout](./GitCheckout.md)

# git checkout

- [Troca de branches](#troca-de-branches)
- [Criando uma branch com -b](#criando-uma-branch-com--b)
- [Checkout de commits](#checkout-de-commits)
- [Detached HEAD](#detached-head)
- [Checkout de arquivos](#checkout-de-arquivos)
- [Checkout de uma referência para um arquivo](#checkout-de-uma-referência-para-um-arquivo)
- [Alterações não commitadas](#alterações-não-commitadas)
- [git switch e git restore](#git-switch-e-git-restore)

O `git checkout` é usado principalmente para **mudar o estado do repositório**, sendo tradicionalmente utilizado para trocar de branch, acessar um commit específico ou restaurar arquivos.

## Troca de branches

A forma mais comum de utilizar o `checkout` é para trocar para uma branch existente:

```bash
git checkout main
```

Nesse caso, o `HEAD` passa a apontar para a branch `main`.

É possível verificar a branch atual através do `git status`:

```bash
git status
```

Ou listar as branches e identificar a atual pelo `*`:

```bash
git branch
```

```text
* main
  develop
  feature/login
```

## Criando uma branch com -b

A flag `-b` permite **criar uma nova branch e trocar para ela imediatamente**:

```bash
git checkout -b feature/login
```

O comando é equivalente conceitualmente a:

```bash
git branch feature/login
git checkout feature/login
```

A nova branch é criada a partir do commit em que o `HEAD` está atualmente.

Também é possível indicar explicitamente o ponto de partida:

```bash
git checkout -b feature/login develop
```

Nesse caso, a `feature/login` será criada a partir da `develop`.

## Checkout de commits

O `checkout` também pode receber o identificador de um commit:

```bash
git checkout a1b2c3d
```

Isso faz o `HEAD` apontar diretamente para aquele commit, em vez de apontar para uma branch.

Também é possível utilizar referências relativas:

```bash
git checkout HEAD~1
```

Nesse exemplo, o Git acessa o commit imediatamente anterior ao atual.

## Detached HEAD

Quando o `HEAD` aponta diretamente para um commit, e não para uma branch, temos um **Detached HEAD**.

Por exemplo:

```bash
git checkout a1b2c3d
```

O estado fica conceitualmente assim:

```text
HEAD
 ↓
a1b2c3d
```

Em uma situação normal:

```text
HEAD
 ↓
main
 ↓
a1b2c3d
```

O Detached HEAD é útil para **consultar ou testar versões antigas do projeto**.

Porém, se você criar commits nesse estado, eles não estarão associados a uma branch. Se quiser continuar o trabalho, é recomendável criar uma branch:

```bash
git checkout -b minha-branch
```

## Checkout de arquivos

O `checkout` também pode restaurar um arquivo:

```bash
git checkout -- arquivo.txt
```

Nesse caso, o Git restaura o arquivo para o estado conhecido pelo Git, descartando alterações locais naquele arquivo.

> **Cuidado:** alterações não commitadas podem ser perdidas.

É recomendável verificar o estado antes:

```bash
git status
git diff
```

O `--` serve para separar a referência das opções dos caminhos dos arquivos:

```text
git checkout -- arquivo.txt
            ↑
       início dos paths
```

## Checkout de uma referência para um arquivo

É possível pegar um arquivo de outra branch ou commit sem trocar de branch.

Por exemplo:

```bash
git checkout main -- arquivo.txt
```

Isso significa:

> Pegue `arquivo.txt` a partir da `main`.

Também é possível utilizar um commit:

```bash
git checkout a1b2c3d -- arquivo.txt
```

Nesse caso, o arquivo será obtido do commit especificado.

Essa forma é especialmente útil quando você quer recuperar apenas um arquivo de outro ponto do histórico.

## Alterações não commitadas

Se existirem alterações locais que seriam sobrescritas pela troca de branch, o Git normalmente impede o `checkout`:

```bash
git checkout develop
```

Se as alterações locais entrarem em conflito com os arquivos de `develop`, o Git pode retornar uma mensagem indicando que suas alterações seriam sobrescritas.

Uma opção é guardar temporariamente as alterações:

```bash
git stash
git checkout develop
```

Depois, elas podem ser recuperadas:

```bash
git stash pop
```

Outra opção é fazer um commit antes de trocar de branch:

```bash
git add .
git commit -m "WIP"
git checkout develop
```

## git switch e git restore

O `git checkout` possui vários comportamentos diferentes. Por isso, versões modernas do Git introduziram comandos mais específicos.

O `git switch` é utilizado para **branches**:

```bash
git switch main
```

Para criar e trocar para uma branch:

```bash
git switch -c feature/login
```

Já o `git restore` é utilizado para **arquivos**:

```bash
git restore arquivo.txt
```

Para recuperar um arquivo de outra referência:

```bash
git restore --source main -- arquivo.txt
```

A relação pode ser resumida assim:

| Objetivo | `checkout` | Comando moderno |
|---|---|---|
| Trocar de branch | `git checkout main` | `git switch main` |
| Criar branch | `git checkout -b feature` | `git switch -c feature` |
| Acessar commit | `git checkout a1b2c3d` | `git switch --detach a1b2c3d` |
| Restaurar arquivo | `git checkout -- arquivo.txt` | `git restore arquivo.txt` |
| Arquivo de outra referência | `git checkout main -- arquivo.txt` | `git restore --source main -- arquivo.txt` |

O `git checkout` continua sendo importante porque aparece frequentemente em projetos, tutoriais e documentação mais antigos. Porém, ao escrever comandos novos, é preferível utilizar `git switch` para branches e `git restore` para arquivos.
