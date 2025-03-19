<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [High Order Functions](./FunctionsEllipsis.md)

# High Order Functions

Em Python, uma high-order function (ou função de alta ordem) é uma função que aceita outra função como argumento ou retorna uma função como resultado.

## Funções que recebem funções como argumento
```python
def quadrado(x):
    return x ** 2

numeros = [1, 2, 3, 4]

# map() recebe a função quadrado como argumento
resultados = map(quadrado, numeros)
print(list(resultados))  # [1, 4, 9, 16]
```

## Funções que retornam funções
```python
def multiplicador(n):
    def multiplica(x):
        return x * n  # Função interna usa "n" do escopo externo
    return multiplica  # Retorna a função interna

# Criando funções específicas
dobrar = multiplicador(2) #O argumento aqui é o n do multiplicador
triplicar = multiplicador(3)

print(dobrar(5))  # 10
print(triplicar(5))  # 15
```