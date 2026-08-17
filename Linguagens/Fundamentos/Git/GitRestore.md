<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git restore](./GitRestore.md)

- [--worktree](#--worktree)
- [--staged](#--staged)
- [--patch](#--patch)
- [--source](#--source)
- [TLDR](#tldr)

# git restore

O comando `git restore` é usado principalmente para desfazer alterações em arquivos do repositório.

Ele pode atuar sobre:

- o working tree — arquivos que foram modificados, mas ainda não foram adicionados ao staging;
- o staging area — arquivos que foram adicionados com git add.

> **Importante**: git restore substitui o conteúdo atual do arquivo por outra versão. Portanto, dependendo do comando utilizado, alterações podem ser perdidas.

Podemos desfazer as alterações do arquivo, fazendo o [Git](./Index.md) recuperar a versão do arquivo presente no último [commit](./Commit.md) (HEAD).

```bash
git restore arquivo.txt
```

Podemos especificar vários arquivos:
```bash
git restore arquivo1.txt arquivo2.txt arquivo3.txt
```

Ou podemos usar um padrão:
```bash
git restore '*.txt'
```

Para restaurar todos os arquivos do diretório atual:
```bash
git restore .
```
Isso descarta as alterações não commitadas desses arquivos no working tree.

# --worktree
A flag --worktree especifica que queremos restaurar o working tree.

```bash
git restore --worktree arquivo.txt
```
Na prática, este é o comportamento padrão do `git restore`:
```bash
git restore arquivo.txt
```

# --staged
Ao aplicarmos o [`git add`](./GitAdd.md), o arquivo adicionado passa para a [staging area](./Staging.md).

Através do `git restore --staged` para retirar um arquivo da área de staging. O conteúdo do arquivo não é perdido. A alteração simplesmente deixa de estar no staging.

```bash
git restore --staged arquivo.txt
```

# --patch
A opção `--patch` permite escolher quais partes das alterações queremos restaurar.

```bash
git restore --patch arquivo.txt
```

O Git apresenta as alterações individualmente e pergunta se queremos restaurá-las. Ele devolverá uma mudança por vez, com a seguinte mensagem `Discard this hunk from worktree [y,n,q,a,d,s,e,?]?`.

Segue a legenda das opções de resposta: 
| Opção | Significado                                                    |
| ----- | -------------------------------------------------------------- |
| `y`   | **Yes** — descarta este *hunk* (bloco de alterações)           |
| `n`   | **No** — mantém este *hunk*                                    |
| `q`   | **Quit** — sai imediatamente; não processa os próximos *hunks* |
| `a`   | **All** — descarta este e todos os *hunks* restantes           |
| `d`   | **Don't** — mantém este e todos os *hunks* restantes           |
| `s`   | **Split** — tenta dividir o *hunk* em partes menores           |
| `e`   | **Edit** — permite editar manualmente o *hunk*                 |
| `?`   | **Help** — mostra a explicação dessas opções                   |

# --source
Por padrão, o git restore usa o [HEAD](./Head.md) como fonte.

Podemos mudar essa fonte usando:

```bash
git restore --source=<commit> arquivo.txt
```

Por exemplo:

```bash
git restore --source=HEAD~1 arquivo.txt
```

Aqui, HEAD~1, significa o commit imediatamente anterior ao HEAD. O Git pega a versão de arquivo.txt daquele commit e coloca essa versão no working tree.

Podemos também usar o hash de um commit:

```bashs
git restore --source=a1b2c3d arquivo.txt
```

Ou uma branch:
```bash
git restore --source=main arquivo.txt
```

Um ponto importante, alterar o source para `HEAD~1` ou um commit anterior **não faz o Git voltar para o commit anterior.** Ele apenas pega um arquivo daquele commit e apenas o conteúdo de arquivo.txt é recuperado, mas continuamos no último commit `HEAD`.

Isso é diferente de comandos como:

- [`git switch`](./GitSwitch.md)
- [`git reset`](./GitReset.md)
- [`git revert`](./GitRevert.md)

que possuem funções relacionadas ao histórico, branches ou commits.

# TLDR
Resumo das principais opções:

|Comando|Efeito|
|---|---|
|`git restore arquivo.txt`|Restaura o working tree|
|`git restore --worktree arquivo.txt`|Restaura o working tree|
|`git restore --staged arquivo.txt`|Remove o arquivo do staging|
|`git restore --staged --worktree arquivo.txt`|Restaura staging e working tree|
|`git restore --source=COMMIT arquivo.txt`|Usa outro commit como fonte|
|`git restore --patch arquivo.txt`|Permite escolher alterações individualmente|
|`git restore .`|Restaura os arquivos do working tree|
|`git restore --staged .`|Remove os arquivos do staging|
