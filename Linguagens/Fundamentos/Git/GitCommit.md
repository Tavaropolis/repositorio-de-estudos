 <link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [Git Commit](./GitCommit.md)

# Git Commit

- [O que é o git commit?](#o-que-é-o-git-commit)
- [Fluxo de trabalho](#fluxo-de-trabalho)
- [Criando um commit](#criando-um-commit)
- [Escrevendo mensagens de commit](#escrevendo-mensagens-de-commit)
- [Consultando commits](#consultando-commits)
- [Alterando o último commit](#alterando-o-último-commit)
- [Resumo dos comandos](#resumo-dos-comandos)

## O que é o git commit?

O comando `git commit` registra um conjunto de alterações no histórico do repositório.

Um commit representa um ponto na história do projeto, permitindo consultar versões anteriores e acompanhar a evolução do código.

**Importante:** o `git commit` registra as alterações que estão na área de staging ([*staging area*](./EstadosGit.md)), e não todas as modificações existentes no diretório de trabalho.

## Fluxo de trabalho

O fluxo básico do Git possui três etapas principais:

1. **Working Directory:** onde você modifica e cria arquivos.
2. **Staging Area:** onde você seleciona as alterações que farão parte do próximo commit.
3. **Repository:** onde os commits são armazenados no histórico local.

```bash
# Verifica o estado dos arquivos
git status

# Adiciona as alterações à área de staging
git add arquivo.txt

# Registra as alterações em um commit
git commit -m "Adiciona arquivo de configuração"
```

Nesse exemplo, somente as alterações adicionadas ao staging serão incluídas no commit.

## Criando um commit

### `git commit -m`

A opção `-m` permite informar a mensagem do commit diretamente no terminal.

```bash
git commit -m "Corrige validação de login"
```

A mensagem deve resumir o propósito das alterações realizadas.

### `git commit` sem `-m`

```bash
git commit
```

Abre o editor de texto configurado no Git para que você escreva a mensagem do commit. Depois de salvar e fechar o editor, o Git concluirá a operação.

### `git commit -a`

```bash
git commit -a -m "Atualiza validação de login"
```

A opção `-a` adiciona automaticamente ao commit as modificações e remoções de arquivos que já são rastreados pelo Git (*tracked*).

**Atenção:** ela não inclui arquivos novos (*untracked*) e não substitui o `git add` para esses arquivos.

## Escrevendo mensagens de commit

Uma mensagem de commit deve ser curta, clara e indicar o objetivo das alterações.

Exemplos:

```bash
git commit -m "Adiciona autenticação por token"
git commit -m "Corrige erro na validação de email"
git commit -m "Remove método não utilizado"
```

Prefira descrever o que foi feito, em vez de usar mensagens genéricas como:

```bash
git commit -m "Alterações"
git commit -m "Correções"
git commit -m "Teste"
```

## Consultando commits

### `git log`

Exibe o histórico de commits do repositório.

```bash
git log
```

### `git log --oneline`

Exibe uma versão resumida do histórico, com o identificador e a mensagem de cada commit.

```bash
git log --oneline
```

Exemplo de saída:

```text
a1b2c3d Corrige validação de login
e4f5g6h Adiciona autenticação por token
i7j8k9l Cria estrutura inicial do projeto
```

Os identificadores acima são apenas exemplos.

## Alterando o último commit

### `git commit --amend`

Permite modificar o commit mais recente, por exemplo, para corrigir sua mensagem ou incluir alterações esquecidas.

Corrigindo a mensagem:

```bash
git commit --amend -m "Corrige validação de login"
```

Incluindo alterações adicionais:

```bash
git add arquivo.txt
git commit --amend --no-edit
```

A opção `--no-edit` mantém a mensagem atual do commit.

**Atenção:** o `--amend` substitui o commit anterior por um novo, com outro identificador. Se o commit já tiver sido enviado para um repositório remoto e outras pessoas dependerem dele, alterar seu histórico pode causar problemas.

## Resumo dos comandos

| Comando | Descrição |
|---|---|
| `git commit -m "mensagem"` | Cria um commit com a mensagem informada. |
| `git commit` | Abre o editor para escrever a mensagem. |
| `git commit -a -m "mensagem"` | Inclui modificações e remoções de arquivos tracked, sem incluir untracked. |
| `git commit --amend` | Substitui o último commit por uma nova versão. |
| `git commit --amend --no-edit` | Atualiza o último commit sem alterar sua mensagem. |
| `git log` | Exibe o histórico de commits. |
| `git log --oneline` | Exibe o histórico em formato resumido. |

## Observações importantes

- O `git commit` atua no histórico **local**. Para enviar os commits a um repositório remoto, normalmente você utiliza `git push`.
- Arquivos untracked precisam ser adicionados com `git add` antes de entrarem em um commit.
- Alterações feitas depois de um `git add` não entram automaticamente no staging: se quiser incluí-las, execute `git add` novamente.
- Um commit não precisa conter todas as alterações existentes no projeto. Você pode selecionar exatamente o que deseja registrar.