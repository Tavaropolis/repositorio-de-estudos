<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git add](./GitAdd.md)

# git add

- [. , -a e --all](#---a-e---all)
- [-u](#-u)
- [-p](#-p)
- [-f](#-f)

O comando `git add` é a porta de entrada para o controle de versão no Git. Sua função principal é mover alterações do [working directory](./Working.md) para a [staging area](./EstadosGit) (índice), preparando-as para serem incluídas no próximo [commit](./Commit.md).

```bash
git add <caminho_do_arquivo>
```

# . , -a e --all
Ao invés de adicionar arquivo por arquivo, é possível adicionar todos os arquivos modificados de uma vez através do `.`, `-a` ou `--all`:

```bash
git add .
```

```bash
git add -a
```

```bash
git add --all
```

# -u 
Esta flag adiciona apenas os arquivos que já são rastreados pelo Git (modificados ou excluídos). Ela não adiciona arquivos novos (untracked).

```bash
git addd -u
```

# -p
O comando git add `-p` (onde -p significa patch) é uma das ferramentas mais avançadas e úteis do Git para manter um histórico de commits limpo, organizado e atômico.

```bash
git add -p
```

Quando o Git para em um hunk, ele vai devolver algo assim no terminal `Stage this hunk [y,n,q,a,d,/,e,?]?`. Você pode pressionar uma tecla correspondente à ação desejada. As principais opções são:

- `y (yes)`: Adiciona este hunk (bloco) à staging area.
- `n (no)`: Ignora este hunk, mantendo-o apenas no diretório de trabalho.
- `q (quit)`: Sai do modo interativo imediatamente (as escolhas feitas até agora são salvas).
- `a (all)`: Adiciona este hunk e todos os outros restantes do arquivo atual ao staging.
- `d (do not)`: Ignora este hunk e todos os outros restantes do arquivo atual.
- `e (edit)`: Permite abrir o bloco manualmente em um editor de texto para alterar linhas específicas antes de enviá-lo ao staging.
- `? (help)`: Exibe a ajuda detalhada com a lista de todos os comandos disponíveis no modo interativo.

# -f
O comando git add -f (onde -f significa force ou forçar) é utilizado para adicionar ao staging arquivos que normalmente seriam ignorados pelo Git. Com isso, pode inclusive adicionar arquivos que caíriam na regra do [.gitignore](./GitIgnore.md).

```bash
git add -f debug.log
```