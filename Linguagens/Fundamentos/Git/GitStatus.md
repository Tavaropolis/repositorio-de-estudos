<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git status](./GitStatus.md)

# git status
O comando `git status` atua como o seu "painel de controle", oferecendo uma visão clara do estado atual do seu repositório local. Ele irá retornar informações como a [branch](./Branch.md) que o susuário está, quantos [commits](./Commit.md) e principalmente quais arquivos foram modificados e/ou se estão na área de staging.

```bash
git status
```

## -s e -v
As duas flags mais comum para esse comando são o `-s` e `-v`. Com o `-s` o git irá retornar uma versão curta (*short*) com os detalhes de status.

```bash
git status -s
```

|Símbolo|Coluna 1 (Staging)|Coluna 2 (Working Directory)|
|---|---|---|
|(espaço)|Inalterado|Inalterado|
|`M`|Modificado e pronto para commit|Modificado, mas não preparado|
|`A`|Adicionado (novo arquivo)|-|
|`D`|Deletado (preparado para remoção)|Deletado (removido localmente)|
|`R`|Renomeado|-|
|`?`|-|Não rastreado (Untracked)|
|`U`|Conflito (Unmerged)|Conflito (Unmerged)|

Exemplos de como interpretar: 
- `??`: O arquivo é novo, o Git não o rastreia e você ainda não executou git add nele.
- `M  (M na esquerda)`: Você executou git add no arquivo após modificá-lo. Ele está pronto para ser enviado no próximo commit.   
- `M (M na direita)`: Você alterou o arquivo no seu editor, mas ainda não executou git add nele.
- `MM`: O arquivo foi modificado, você o adicionou ao staging, mas depois realizou novas alterações no arquivo no working directory sem rodar o git add novamente. 
- `A`: Um arquivo novo que foi adicionado ao staging (via git add).

O oposto do `-s` seria o `-v`, onde traz além das informações comuns já presente no `git status`, o `-v` traz também o que foi modificado no arquivo.

```bash
git status -v
```