<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git config](./GitConfig.md)

# git config

- [As três camadas de configuração](#as-três-camadas-de-configuração)
- [user.name e user.email](#username-e-useremail)
- [--list, --show-scope e --show-origin](#--list---show-scope-e---show-origin)

O `git config` é o comando usado para consultar e alterar as configurações do [Git](./Index.md).

## As três camadas de configuração

As configurações do Git possuem três níveis:

| Nível  |Escopo | Arquivo típico |
|---|---|---|
|`--system`|Todo o sistema|`/etc/gitconfig`|
|`--global`|Seu usuário|`~/.gitconfig` ou `~/.config/git/config`|
|`--local`|Um repositório específico|`.git/config`|

A ordem de prioridade segue a lógica de quanto mais específico, maior a prioridade:

**local** > **global** > **system**

O Git gerencia os diferentes níveis através de arquivos de configurações diferentes. As configurações de `--system` vão geralmente estar salvas na pasta de instalação do git, como a `/Program Files`. As configurações `--global` geralmente vão estar na `/User`. E `--local` geralmente tem suas configurações salvas no `/.git` local do projeto.

## user.name e user.email

É possível adicionar as informações de usuário através das flags `user.name` e `user.email`. Essas informações são gravadas nos commits.

Se usar com a flag `--local` irá valer apenas para aquele repositório.
```bash
git config --local user.name "Seu Nome"
git config --local user.email "seu@email.com"
```

Se usar com a flag `--global` irá afeta seus repositórios em geral.
```bash
git config --global user.name "Seu Nome"
git config --global user.email "seu@email.com"
```

Devido as prioridades, se ouvir um usuário `--local` e um `--global` **o usuário `--local` é o que será considerado**.

`user.name` e `user.email` não são necessariamente seu nome de usuário em uma plataforma como **GitHub**. Eles são os dados de identidade registrados no commit. A plataforma pode posteriormente associar esse e-mail à sua conta.

## --list, --show-scope e --show-origin

É possível verificar as propriedades já configuradas através da flag `--list`.
```bash
git config --list 
```

O retorno segue uma lógica de [chave]=[valor], por exemplo:
```bash
core.symlinks=false
core.ignorecase=true
remote.origin.url=https://github.com/Tavaropolis/repositorio-de-estudos.git
remote.origin.fetch=+refs/heads/*:refs/remotes/origin/*
branch.main.remote=origin
branch.main.merge=refs/heads/main
branch.main.vscode-merge-base=origin/main
```

Adicionando `--show-scope` você adiciona ao retorno o escopo da configuração (se é `--local`, `--global` ou `--system`):
```bash
git config --list  --show-scope
```

Exemplo de retorno:
```bash
system  file:C:/Program Files/Git/etc/gitconfig credential.https://dev.azure.com.usehttppath=true
system  file:C:/Program Files/Git/etc/gitconfig init.defaultbranch=master
local   file:.git/config        core.repositoryformatversion=0
local   file:.git/config        core.filemode=false
```

Por fim, utilizando o `--show-origin` retorna a pasta do sistema onde está declarada a configuração:
```
git config --list --show-scope --show-origin
```