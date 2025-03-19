<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [global](./FunctionsGlobals.md)

# global

As funções atuam em um escopo separado do módulo principal, portanto podemos gerar uma variável com o mesmo nome que não irá gerar um conflito: 

```python
x = 10

def primeira_funcao():
    x = 15
    print(x)

primeira_funcao() #Aqui x é 5
print(x) #Aqui x é 10
```

Os escopos de fora não tem acesso as variáveis dos escopos de dentro. Já os escopos de dentro em acesso as variavéis de fora, mas apenas para leitura, não é possível modificar o valor do x do módulo no nosso exemplo anterior.

Para podermos alterar a variável do módulo de dentro de uma função, podemos utilizar a palavra reservada `global`:

```python
x = 10

def primeira_funcao():
    global x 
    x = 15

primeira_funcao()
print(x) #Saída: 15
```