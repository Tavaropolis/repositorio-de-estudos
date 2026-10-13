<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git remote](./GitRemote.md)

# git remote

- [O que é um remote](#o-que-é-um-remote)
- [git remote](#git-remote)
- [Adicionando um remote](#adicionando-um-remote)
- [origin](#origin)
- [git remote -v](#git-remote--v)
- [git remote get-url](#git-remote-get-url)
- [git remote show](#git-remote-show)
- [Alterando a URL de um remote](#alterando-a-url-de-um-remote)
- [Renomeando um remote](#renomeando-um-remote)
- [Removendo um remote](#removendo-um-remote)
- [Remote não é branch](#remote-não-é-branch)
- [Remotes e operações de rede](#remotes-e-operações-de-rede)

O `git remote` é usado para **gerenciar as conexões entre o repositório local e repositórios remotos**.

Um remote normalmente representa um repositório hospedado em outro lugar, como no GitHub, GitLab ou outro servidor Git.

## O que é um remote

Um repositório local pode conhecer um ou vários repositórios remotos.

Por exemplo:

```text
Repositório local
       │
       ├── origin ──→ repositório remoto
       │
       └── upstream ─→ outro repositório remoto
```

O remote é basicamente um **nome associado à URL de um repositório remoto**.

Por exemplo:

```text
origin → https://github.com/usuario/projeto.git
```

O Git utiliza esse nome para que você não precise informar a URL toda vez que executar operações com aquele repositório.

## git remote

Executar:

```bash
git remote
```

lista os remotes configurados no repositório.

Exemplo:

```text
origin
upstream
```

Se houver apenas um remote, é comum aparecer:

```text
origin
```

## Adicionando um remote

É possível adicionar um remote através de:

```bash
git remote add origin https://github.com/usuario/projeto.git
```

A estrutura do comando é:

```bash
git remote add <nome> <url>
```

Por exemplo:

```bash
git remote add upstream https://github.com/outra-pessoa/projeto.git
```

Nesse caso, a URL foi associada ao nome `upstream`.

## origin

`origin` **não é uma palavra reservada do Git**.

É apenas o nome padrão normalmente utilizado para o remote principal quando um repositório é clonado.

Por exemplo:

```bash
git clone https://github.com/usuario/projeto.git
```

Normalmente o Git configura:

```text
origin → https://github.com/usuario/projeto.git
```

Por isso, comandos como:

```bash
git fetch origin
git push origin main
```

são extremamente comuns.

É possível usar outro nome:

```bash
git remote add servidor https://github.com/usuario/projeto.git
```

Nesse caso:

```bash
git fetch servidor
```

## git remote -v

A flag `-v` mostra as URLs associadas aos remotes:

```bash
git remote -v
```

Exemplo:

```text
origin  https://github.com/usuario/projeto.git (fetch)
origin  https://github.com/usuario/projeto.git (push)
```

Pode existir uma URL diferente para `fetch` e `push`:

```text
origin  https://github.com/usuario/projeto.git (fetch)
origin  git@github.com:usuario/projeto.git (push)
```

Isso permite, por exemplo, buscar dados por uma URL e enviar alterações através de outra.

## git remote get-url

Para consultar diretamente a URL de um remote:

```bash
git remote get-url origin
```

Retorno:

```text
https://github.com/usuario/projeto.git
```

Também é possível consultar a URL de push:

```bash
git remote get-url --push origin
```

## git remote show

O comando:

```bash
git remote show origin
```

mostra informações mais detalhadas sobre o remote.

Entre outras informações, pode indicar:

- URL do remote;
- branch padrão;
- branches remotas;
- branches locais associadas a branches remotas.

É útil para entender como o repositório local está relacionado ao remoto.

## Alterando a URL de um remote

É possível alterar a URL de um remote através de:

```bash
git remote set-url origin https://github.com/novo-usuario/projeto.git
```

A estrutura é:

```bash
git remote set-url <nome> <nova-url>
```

Depois, é possível verificar:

```bash
git remote -v
```

## Renomeando um remote

Para alterar o nome de um remote:

```bash
git remote rename origin upstream
```

A estrutura é:

```bash
git remote rename <nome-atual> <novo-nome>
```

## Removendo um remote

Para remover um remote:

```bash
git remote remove upstream
```

Também existe a forma:

```bash
git remote rm upstream
```

A remoção apenas elimina a referência ao remote do repositório local. Ela **não apaga o repositório remoto**.

## Remote não é branch

É importante não confundir:

```text
origin
origin/main
main
```

Eles representam conceitos diferentes.

### `origin`

É o **nome do remote**.

```text
origin → URL do repositório remoto
```

### `main`

É uma **branch local**.

```text
main → commit local
```

### `origin/main`

É uma **remote-tracking branch**.

Ela representa o estado conhecido localmente da branch `main` do remote `origin`.

Conceitualmente:

```text
Repositório local              Repositório remoto

main ────────────────┐
                     │
origin/main ─────────┼──────→ main
                     │
                  origin
```

O `origin/main` é atualizado quando o Git recebe informações do remote, normalmente através de:

```bash
git fetch
```

## Remotes e operações de rede

O `git remote` **não é o comando que normalmente envia ou baixa commits**.

Ele serve principalmente para **configurar e consultar os remotes**.

As operações de transferência são feitas por outros comandos.

Para baixar informações do remote:

```bash
git fetch origin
```

Para enviar commits:

```bash
git push origin main
```

Para baixar e integrar alterações:

```bash
git pull origin main
```

Podemos resumir:

```text
git remote
    ↓
gerencia a configuração do remote

git fetch
    ↓
busca informações/objetos do remote

git push
    ↓
envia commits para o remote

git pull
    ↓
fetch + integração das alterações
```

## Principais comandos

| Objetivo | Comando |
|---|---|
| Listar remotes | `git remote` |
| Listar remotes + URLs | `git remote -v` |
| Adicionar remote | `git remote add origin <url>` |
| Ver informações do remote | `git remote show origin` |
| Ver URL | `git remote get-url origin` |
| Alterar URL | `git remote set-url origin <url>` |
| Renomear remote | `git remote rename origin novo-nome` |
| Remover remote | `git remote remove origin` |

O ponto principal é:

> **Um remote é um nome local associado a um repositório Git remoto.**

Por isso, quando você executa:

```bash
git push origin main
```

o Git interpreta:

```text
origin → qual repositório remoto?
main   → qual branch quero enviar?
```

`git remote` é, portanto, o comando usado para **gerenciar essa relação entre o repositório local e seus repositórios remotos**.
