<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [Estados de um Arquivo no Git](./EstadosGit.md)

- [Untracked](#1-untracked-não-rastreado)
- [Staged](#2-staged-preparado)
- [Unmodified](#3-unmodified-não-modificado)
- [Modified](#4-modified-modificado)
- [Tabela de Referência Rápida](#tabela-de-referência-rápida)

# Estados de um Arquivo no Git

Para dominar o [Git](./Index.md), é fundamental entender que o Git não monitora apenas "alterações", ele gerencia o **estado** em que um arquivo se encontra em relação ao repositório. Existem 4 estados principais.

## 1. Untracked (Não rastreado)
Este é o estado inicial de qualquer arquivo novo criado na pasta do projeto.

*   **O que significa:** O Git "vê" que o arquivo existe no seu diretório, mas ele não faz parte do seu controle de versão.
*   **Detalhe importante:** O Git não rastreia nada automaticamente. Se você criar um arquivo, ele será `Untracked` até que você o adicione explicitamente ([`git add`](./GitAdd.md)). Isso evita que arquivos temporários, logs ou lixo da IDE sejam adicionados ao repositório por acidente.
*   **Comando:** `git status` (o arquivo aparece em vermelho).

## 2. Staged (Preparado)
Ocorre quando você marca um arquivo (novo ou modificado) para fazer parte do próximo `commit`.

*   **O que significa:** O arquivo está na "Área de Preparação" (Staging Area). Você tirou um "snapshot" (foto) do conteúdo atual daquele arquivo e ele está pronto para ser gravado no histórico.
*   **Observação:** Um arquivo pode estar `Tracked` e `Staged` ao mesmo tempo.
*   **Comando:** `git add <arquivo>`. Após isso, o `git status` mostra o arquivo em verde.

## 3. Unmodified (Não modificado)
O arquivo está em seu estado original, idêntico ao que foi registrado no último `commit`.

*   **O que significa:** O arquivo já é `Tracked` (o Git já o conhece), mas você não alterou o conteúdo dele desde o último salvamento oficial.
*   **Nota:** O Git sabe disso comparando o *hash* do arquivo no disco com o *hash* armazenado no commit anterior.

## 4. Modified (Modificado)
O arquivo já foi rastreado pelo Git, mas você alterou o conteúdo dele desde o último `commit` e ainda não o preparou (`git add`) para o próximo.

*   **O que significa:** Existe uma diferença entre o que está no seu disco e o que foi registrado no seu último commit.
*   **Comando:** [`git diff`](./GitDiff.md) mostra exatamente o que mudou neste arquivo.

## Tabela de Referência Rápida

| Estado | O Git conhece o arquivo? | Diferença do último commit? |
| :--- | :--- | :--- |
| **Untracked** | Não | N/A |
| **Unmodified** | Sim | Não |
| **Modified** | Sim | Sim |
| **Staged** | Sim | Sim (Pronto para commit) |