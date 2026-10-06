<link rel="stylesheet" type="text/css" href="../../../CSS/dark-theme.css">

[Anotações](../../) > [Fundamentos](../Index.md) > [Git](./Index.md) > [git log](./GitLog.md)

# git log
Por padrão, o `git log` lista todos os commits do histórico em ordem cronológica inversa (do mais recente para o mais antigo).

```bash
git log
```
O comando retornará os seguintes dados:
- Hash do commit (SHA-1)
- Autor
- Data
- Mensagem do commit

## --oneline
Mostra cada commit em apenas uma linha. Ideal para ter uma visão panorâmica. 
```bash
git log --oneline`
```
É possível delimitar o número de linhas através do `-n`:

```bash
git log --oneline -n 3
```

Exemplo do retorno do comando:
```bash
a1b2c3d Refatora o serviço de autenticação
e4f5g6h Adiciona validação de email no cadastro
7i8j9k0 Corrige erro de digitação no README
```

## --patch
Mostra o histórico detalhado acompanhado do diff (exatamente o que foi alterado linha por linha) em cada commit. Também é possível definir o número de linhas com o `-n`.
```bash
git log --patch -n 1
```

É possível ainda usar o `-p` ao invés do `--patch` que traz o mesmo resultado:

```bash
git log -p -n 1
```

Exemplo do retorno do comando:
```bash
commit a1b2c3d4e5f67890123456789abcdef012345678
Author: Gabriel <gabriel@email.com>
Date:   Tue Aug 18 10:00:00 2026 -0300

    Refatora o serviço de autenticação

diff --git a/src/AuthService.java b/src/AuthService.java
index 83db4fc..4f2a11b 100644
--- a/src/AuthService.java
+++ b/src/AuthService.java
@@ -15,7 +15,7 @@ public class AuthService {
     public boolean validateToken(String token) {
         if (token == null) {
            return false;
        throw new IllegalArgumentException("Token cannot be null");
     }
     return jwtDecoder.decode(token) != null;
 }
```

## --stat
Exibe um resumo estatístico após cada commit, listando quais arquivos foram modificados e a quantidade de inserções/remoções. Também é possível definir o número de linhas com o `-n`.

```bash
git log --stat -n 2
```

Exemplo do retorno do comando:
```bash
commit a1b2c3d4e5f67890123456789abcdef012345678
Author: Gabriel <gabriel@email.com>
Date:   Tue Aug 18 10:00:00 2026 -0300

    Refatora o serviço de autenticação

 src/AuthService.java | 2 +-
 src/AuthTest.java    | 5 +++++
 2 files changed, 6 insertions(+), 1 deletion(-)

commit e4f5g6h7i8j9k0123456789abcdef01234567890
Author: Gabriel <gabriel@email.com>
Date:   Mon Aug 17 16:30:00 2026 -0300

    Adiciona validação de email no cadastro

 src/UserService.java | 10 ++++++++++
 1 file changed, 10 insertions(+)
```