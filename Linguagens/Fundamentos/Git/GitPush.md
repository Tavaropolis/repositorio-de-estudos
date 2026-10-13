<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git push](./GitPush.md)

# git push

- [O que é `git push`](#o-que-é-git-push)
- [Sintaxe básica](#sintaxe-básica)
- [Enviando uma branch](#enviando-uma-branch)
- [Definindo o upstream com `-u`](#definindo-o-upstream-com--u)
- [O que é enviado pelo push](#o-que-é-enviado-pelo-push)
- [Principais flags](#principais-flags)
- [Excluindo uma branch remota](#excluindo-uma-branch-remota)
- [Erros comuns](#erros-comuns)
- [Push para vários remotes](#push-para-vários-remotes)
- [Resumo](#resumo)

O `git push` é usado para **enviar commits do repositório local para um repositório remoto**.

Por exemplo, depois de criar um commit localmente, você pode enviá-lo ao GitHub:

```bash
git push origin main
```

O `push` não envia simplesmente os arquivos alterados: ele publica referências e os objetos Git necessários para que o remoto passe a conter os commits enviados.

## O que é `git push`

Imagine que o histórico local esteja assim:

```text
A---B---C    main
```

Enquanto o remoto ainda está em:

```text
A---B        origin/main
```

Ao executar:

```bash
git push origin main
```

o commit `C` é enviado, e a branch remota passa a apontar para ele. A referência local `origin/main`, que acompanha o estado conhecido da branch remota, também costuma ser atualizada.

## Sintaxe básica

```bash
git push <remote> <branch>
```

Exemplo:

```bash
git push origin main
```

- `origin`: nome do remote.
- `main`: branch local que será enviada para a branch remota correspondente.

Para enviar uma branch local com outro nome para uma branch remota específica, use um *refspec*:

```bash
git push origin minha-branch:branch-remota
```

A forma geral é `origem-local:destino-remoto`. Se os nomes forem iguais, normalmente basta `git push origin minha-branch`.

## Enviando uma branch

Depois de criar uma branch local:

```bash
git switch -c feature/login
```

e criar um ou mais commits, você pode publicá-la:

```bash
git push origin feature/login
```

Se a branch ainda não existir no remoto, o Git normalmente a cria no destino.

```text
feature/login          → branch local
origin/feature/login   → referência local que acompanha a branch remota
```

## Definindo o upstream com `-u`

Upstream é a referência remota associada à sua branch local, usada como padrão em operações como git push e git pull.

Ao publicar uma branch pela primeira vez, é comum usar:

```bash
git push -u origin feature/login
```

`-u` é um atalho para `--set-upstream`. Ele configura a branch remota como *upstream* da branch local.

Depois disso, estando nessa branch, muitas vezes basta executar:

```bash
git push
git pull
```

O Git já sabe qual branch remota usar como referência padrão. Sem o upstream configurado, talvez seja necessário informar o remote e a branch explicitamente.

## O que é enviado pelo push

O `push` publica commits que ainda não estão disponíveis no remoto e atualiza a referência remota solicitada, desde que a atualização seja permitida.

Ele **não envia automaticamente todas as branches locais** em um push comum.

```bash
git push origin main
```

envia a branch `main` para `origin`, não todas as branches existentes no computador.

Para enviar todas as branches locais:

```bash
git push --all origin
```

Isso não significa que arquivos não commitados serão enviados. Para publicar alterações, primeiro crie commits:

```bash
git add .
git commit -m "Implementa login"
git push origin main
```

## Principais flags

### `-u` / `--set-upstream`

Publica a branch e configura seu upstream.

```bash
git push -u origin main
```

### `-f` / `--force`

Força a atualização da referência remota mesmo quando ela não seria aceita como avanço normal.

```bash
git push --force origin main
```

**Cuidado:** pode substituir o histórico apontado pela branch remota e tornar commits de outras pessoas inacessíveis por essa referência. Evite usar sem entender o impacto.

### `--force-with-lease`

Também permite uma atualização forçada, mas verifica se a referência remota ainda está no estado esperado pelo seu repositório local.

```bash
git push --force-with-lease origin minha-branch
```

É geralmente mais seguro do que `--force`, mas ainda pode sobrescrever trabalho remoto. Não é uma garantia absoluta contra todos os cenários de perda de trabalho.

### `--all`

Envia todas as branches locais para o remote indicado.

```bash
git push --all origin
```

Não inclui automaticamente todas as tags.

### `--tags`

Envia todas as tags locais.

```bash
git push --tags origin
```

Para enviar uma tag específica:

```bash
git push origin v1.0.0
```

### `--delete`

Exclui uma branch no remoto.

```bash
git push origin --delete feature/login
```

Isso remove a branch remota; não apaga automaticamente a branch local com o mesmo nome.

### `--dry-run`

Mostra o que seria feito sem realizar a atualização remota.

```bash
git push --dry-run origin main
```

### `-v` / `--verbose`

Mostra informações mais detalhadas durante a operação.

```bash
git push -v origin main
```

## Excluindo uma branch remota

A forma mais direta é:

```bash
git push origin --delete nome-da-branch
```

Para excluir também a branch local, use separadamente:

```bash
git branch -d nome-da-branch
```

O `-d` só permite excluir uma branch local que o Git considere já integrada. Para forçar a exclusão local, existe `-D`; verifique antes se não há trabalho que você precise preservar.

## Erros comuns

### `rejected (non-fast-forward)`

Pode ocorrer quando a branch remota tem commits que não estão presentes na sua branch local.

```text
Remoto: A---B---C
Local:  A---B---D
```

O Git recusa o push porque atualizar diretamente para `D` faria a branch remota deixar de apontar para `C`.

Em geral, integre primeiro as mudanças remotas e depois tente novamente:

```bash
git pull --rebase origin main
git push origin main
```

Use a estratégia apropriada para o projeto. Não recorra automaticamente a `--force`.

### `src refspec main does not match any`

Pode acontecer se a branch local `main` não existir ou se ainda não houver um commit para enviar.

```bash
git branch
git status
```

Se for um repositório novo, crie o primeiro commit antes de tentar publicar a branch.

### Não há upstream configurado

Se o Git não souber qual branch remota usar, informe-a explicitamente:

```bash
git push -u origin main
```

Depois de configurar o upstream, os próximos `git push` nessa branch podem ser mais simples.

## Push para vários remotes

Um repositório local pode ter mais de um remote:

```bash
git remote -v
```

Para enviar a branch para cada remote separadamente:

```bash
git push origin main
git push bitbucket main
```

Um push para `origin` não atualiza automaticamente `bitbucket`, a menos que o remote esteja configurado deliberadamente com múltiplas URLs de push.

## Resumo

| Objetivo | Comando |
|---|---|
| Enviar uma branch | `git push origin main` |
| Publicar branch e configurar upstream | `git push -u origin feature` |
| Enviar todas as branches locais | `git push --all origin` |
| Enviar todas as tags | `git push --tags origin` |
| Excluir branch remota | `git push origin --delete feature` |
| Simular a operação | `git push --dry-run origin main` |
| Atualização forçada com mais proteção | `git push --force-with-lease origin feature` |
| Mostrar mais detalhes | `git push -v origin main` |

### Modelo mental

```text
working tree
    │
    │ git add
    ▼
staging area
    │
    │ git commit
    ▼
histórico local
    │
    │ git push
    ▼
histórico / branch remota
```

A regra principal é: **`git commit` registra as mudanças localmente; `git push` publica commits no remoto**.
