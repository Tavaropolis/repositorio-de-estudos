 <link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git clean](./GitClean.md)

# git clean

- [O que é o git clean?](#o-que-é-o-git-clean)
- [Visualizando o que será removido](#visualizando-o-que-será-removido)
- [Removendo arquivos não rastreados](#removendo-arquivos-não-rastreados)
- [Removendo diretórios](#removendo-diretórios)
- [Removendo arquivos ignorados](#removendo-arquivos-ignorados)
- [Opções do git clean](#opções-do-git-clean)
- [Resumo](#resumo)

## O que é o git clean?

O comando `git clean` remove arquivos e diretórios **não rastreados pelo Git** (*untracked*).

Ele é útil quando você deseja limpar arquivos temporários, arquivos gerados por ferramentas de build ou outros arquivos que não fazem parte do controle de versão.

Por exemplo, considere o seguinte estado:

```text
projeto/
├── README.md       # Rastreado pelo Git
├── app.js          # Rastreado pelo Git
├── teste.tmp       # Não rastreado
└── build/          # Diretório não rastreado
```

O `git clean` pode remover `teste.tmp` e, com as opções adequadas, o diretório `build/`.

**Atenção:** os arquivos removidos não são enviados para a Lixeira pelo Git e podem não ser recuperáveis. Por isso, é importante conferir o que será excluído antes de executar o comando.

## Visualizando o que será removido

Antes de remover os arquivos, utilize a opção `-n` (*dry run*) para simular a operação:

```bash
git clean -n
```

O comando lista os arquivos que seriam removidos, sem excluí-los.

Essa é uma boa prática antes de executar uma limpeza real.

## Removendo arquivos não rastreados

Para remover os arquivos não rastreados listados pela simulação, utilize:

```bash
git clean -f
```

A opção `-f` (*force*) confirma a execução da remoção.

Por padrão, o comando não remove diretórios não rastreados. Para incluir diretórios, utilize `-d`:

```bash
git clean -fd
```

É possível combinar as opções para simular a remoção de arquivos e diretórios:

```bash
git clean -nd
```

## Removendo arquivos ignorados

Arquivos listados no `.gitignore` normalmente são ignorados pelo `git clean`.

Para incluir arquivos ignorados na limpeza, utilize `-x`:

```bash
git clean -fx
```

Para incluir também os diretórios não rastreados:

```bash
git clean -fdx
```

Essa combinação pode remover arquivos de configuração local, dependências instaladas e outros arquivos que você talvez queira manter. Use com cuidado.

A opção `-X`, com X maiúsculo, remove apenas os arquivos ignorados pelo Git:

```bash
git clean -fX
```

## Opções do git clean

| Opção | Função |
|---|---|
| `-n` | Simula a operação e mostra o que seria removido. |
| `-f` | Força a remoção dos arquivos não rastreados. |
| `-d` | Inclui diretórios não rastreados na remoção. |
| `-x` | Inclui arquivos ignorados pelo `.gitignore`. |
| `-X` | Remove apenas arquivos ignorados pelo Git. |
| `-i` | Abre um modo interativo para escolher o que remover. |

O modo interativo pode ser iniciado com:

```bash
git clean -i
```

Ele permite examinar os itens e escolher quais deseja excluir.

## Resumo

- `git clean` remove arquivos não rastreados pelo Git.
- `git clean -n` permite verificar o que seria removido antes de executar a operação.
- `git clean -f` remove arquivos não rastreados.
- `git clean -fd` inclui diretórios não rastreados.
- `git clean -fdx` também inclui arquivos ignorados pelo `.gitignore`.
- `git clean -fX` remove somente arquivos ignorados.
- Os arquivos removidos podem não ser recuperáveis; prefira simular a operação antes da exclusão real.