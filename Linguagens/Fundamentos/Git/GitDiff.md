<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git diff](./GitDiff.md)

- [--staged e --cached](#--staged-e---cached)
- [--stat](#--stat)
- [--name-only](#--name-only)
- [--name-status](#--name-status)
- [TLDR](#tldr)

# git diff
O comando `git diff` é usado para visualizar diferenças entre versões de arquivos. Ele é especialmente útil para descobrir:

- quais linhas foram modificadas;
- o que ainda não foi colocado no staging;
- o que está no staging e será incluído no próximo commit;
- diferenças entre commits;
- diferenças entre branches.

Se utilizarmos o comando:
```bash
git diff
```
Será retornado algo mais ou menos com essa estrutura:

```
diff --git a/arquivo.txt b/arquivo.txt 
index 1234567..abcdefg 100644 
--- a/arquivo.txt 
+++ b/arquivo.txt 
@@ -1,2 +1,3 @@ 
 Primeira linha
 Segunda linha 
+Nova linha
```

Explicando os símbolos do retorno:
- `+` — Linha adicionada
- `-` — Linha removida
- `Espaço no início` - Linha sem alteração
- `---` — Arquivo antigo
- `+++` — Arquivo novo
- `@@` — Cabeçalho do hunk
- `index` — Contém informações internas do Git sobre os objetos que representam as versões do arquivo.

Explicando o cabeçalho do hunk:
Um hunk como o do exemplo `@@ -10,4 +10,6 @@` significa:

Versão antiga → começa na linha 10, 4 linhas
Versão nova   → começa na linha 10, 6 linhas

> **IMPORTANTE: Arquivos novos criados dentro do repositório são considerados como untracked pelo Git e portanto não aparecerão em um `git diff` simples. Para vizualiza-los é necessário colocar em staging e utilizar o `git diff --staged`**

## --staged e --cached
O `git diff` sem opções compara especificamente o **staging area** com o **working tree**. Portando apenas chamar um `git diff` quando os arquivos já estão em staging, não irá devolver nada no terminal. Para visualizar o que está no staging:

```bash
git diff --staged
```
Também podemos escrever (as duas formas são equivalentes):
```bash
git diff --cached
```

## --stat
Se não queremos ver todas as linhas modificadas, podemos pedir apenas um resumo:
```bash
git diff --stat
``` 
O retorno será algo como:
```bash
arquivo.txt | 5 ++++- 
main.py | 8 +++++--- 
app.js | 3 ++- 

3 files changed, 11 insertions(+), 5 deletions(-)
```
Explicando o retorno: 
- `arquivo.txt` — Nome do arquivo
- `|` — Separador
- `5` — Número de alterações
- `+` — Inserção de linha
- `-` — Remoção de linha

Note que a soma de `+` e `-` é o valor de modificações no arquivo.

## --name-only
Mostra apenas os nomes dos arquivos modificados:

```bash
git diff --name-only
```
Exemplo de retorno:
```
arquivo.txt
main.py
app.js
```

## --name-status
Além do nome, mostra o tipo de alteração:

```bash
git diff --name-status
```

Exemplo de retorno:
```bash
M   arquivo.txt
A   novo.txt
D   antigo.txt
```

Onde:

- `M` — Modified
- `A` — Added
- `D` — Deleted

## TLDR
| Comando                   | O que mostra                             |
| ------------------------- | ---------------------------------------- |
| `git diff`                | Working tree ↔ staging                   |
| `git diff --staged`       | Staging ↔ HEAD                           |
| `git diff --cached`       | Igual a `--staged`                       |
| `git diff HEAD`           | Working tree ↔ HEAD                      |
| `git diff A B`            | Diferença entre dois commits/referências |
| `git diff -- arquivo.txt` | Diff de um arquivo específico            |
| `git diff --stat`         | Resumo das alterações                    |
| `git diff --name-only`    | Apenas nomes dos arquivos                |
| `git diff --name-status`  | Nomes + tipo de alteração                |
| `git diff --check`        | Verifica problemas de whitespace         |
| `git diff --word-diff`    | Mostra diferenças por palavra            |
| `git diff -U0`            | Sem linhas de contexto                   |