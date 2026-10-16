 <link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [Pull Request](./GitHubPullRequest.md)

# Pull Request

- [O que é um Pull Request?](#o-que-é-um-pull-request)
- [Como funciona](#como-funciona)
- [Criando um Pull Request a partir de um Fork](#criando-um-pull-request-a-partir-de-um-fork)
- [Atualizando um Pull Request](#atualizando-um-pull-request)
- [O que acontece depois da aprovação?](#o-que-acontece-depois-da-aprovação)
- [Pull Request, Fork e Merge](#pull-request-fork-e-merge)
- [Resumo](#resumo)

## O que é um Pull Request?

Um **Pull Request (PR)** é uma solicitação para que alterações feitas em uma branch sejam revisadas e, se aprovadas, integradas a outra branch.

Ele é muito usado no GitHub para propor mudanças em um projeto sem precisar ter permissão para alterar diretamente o repositório original.

Apesar do nome, criar um Pull Request não executa automaticamente um [`git pull`](./GitPull.md) e não integra as alterações por conta própria. O PR é uma proposta que pode ser discutida, revisada, aprovada ou rejeitada.

## Como funciona

Imagine que você criou uma branch chamada `feature/login` e deseja integrar suas alterações à branch `main`.

O fluxo básico é:

1. Fazer alterações e criar commits na branch de trabalho.
2. Enviar a branch ao repositório remoto.
3. Abrir um Pull Request indicando a branch de origem e a branch de destino.
4. Permitir que outras pessoas revisem o código, comentem e solicitem mudanças.
5. Depois da aprovação, integrar as alterações, caso o projeto permita.

Para enviar a branch ao remoto:

```bash
git push origin feature/login
```

No GitHub, você poderá abrir um PR com:

- **Base:** `main` — a branch que receberá as alterações.
- **Compare:** `feature/login` — a branch que contém as alterações propostas.

Os nomes podem variar conforme o projeto e o fluxo de trabalho.

## Criando um Pull Request a partir de um Fork

Em projetos de terceiros, é comum não ter permissão para enviar branches diretamente ao repositório original. Nesse caso, você pode criar um Fork, trabalhar nele e abrir um PR para o projeto original.

Considere esta estrutura:

- Repositório original: `autor/projeto`
- Seu Fork: `seu-usuario/projeto`
- Branch criada no Fork: `feature/login`

Primeiro, envie sua branch ao seu Fork:

```bash
git push origin feature/login
```

Nesse exemplo, `origin` aponta para o seu Fork. Depois, no GitHub, crie um Pull Request configurando:

- **Repositório de destino:** `autor/projeto`
- **Branch de destino:** `main`
- **Repositório de origem:** `seu-usuario/projeto`
- **Branch de origem:** `feature/login`

O GitHub compara as alterações da branch do seu Fork com a branch de destino do repositório original. Você não precisa copiar os commits manualmente para o repositório original.

## Atualizando um Pull Request

Um PR acompanha as alterações feitas na branch de origem. Se você adicionar novos commits e enviá-los para a mesma branch, o PR normalmente será atualizado automaticamente.

Por exemplo:

```bash
git switch feature/login

# Faça novas alterações e crie um commit
git add .
git commit -m "Corrige validação do login"

# Envie as atualizações
git push origin feature/login
```

Não é necessário abrir outro PR para cada novo commit da mesma proposta.

## O que acontece depois da aprovação?

A aprovação indica que a revisão foi aceita conforme as regras do projeto, mas não significa necessariamente que o PR será integrado imediatamente. Podem existir verificações automáticas, aprovações adicionais ou outras regras de proteção.

Quando o PR é integrado, o GitHub pode oferecer diferentes estratégias, dependendo da configuração do repositório:

- **Merge commit:** integra as alterações criando um commit de merge.
- **Squash and merge:** reúne os commits do PR em um único commit na branch de destino.
- **Rebase and merge:** reaplica os commits sobre a branch de destino, sem criar um commit de merge tradicional.

A branch de origem não é necessariamente excluída ao integrar o PR. O GitHub pode oferecer a opção de apagá-la, e ela também pode ser removida manualmente depois.

## Pull Request, Fork e Merge

| Conceito | Função |
|---|---|
| **Fork** | Cria uma cópia de um repositório no GitHub, sob outra conta ou organização. |
| **Branch** | Permite trabalhar em uma linha de desenvolvimento separada. |
| **Pull Request** | Propõe alterações de uma branch para outra e permite revisá-las. |
| **Merge** | Integra alterações de uma linha de desenvolvimento a outra. |

**Importante:** criar um Pull Request não é a mesma coisa que executar [`git merge`](./GitMerge.md). O PR organiza a proposta e a revisão; a integração acontece quando alguém com permissão realiza ou autoriza o merge.

## Resumo

- Um Pull Request propõe alterações de uma branch para outra.
- É possível abrir um PR entre branches do mesmo repositório ou entre um Fork e o repositório original.
- A branch de origem deve estar enviada ao GitHub para que suas alterações possam ser comparadas.
- Novos commits enviados à branch de origem normalmente aparecem no PR existente.
- O PR pode ser aprovado, receber comentários, ter alterações solicitadas ou ser fechado sem merge.
- Quando aprovado e integrado, as alterações passam a fazer parte da branch de destino conforme a estratégia de merge escolhida.