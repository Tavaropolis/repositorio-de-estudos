<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Generators](./Generators.md)

# Generators

`Generators` funcionam de maneira similar aos [iterators](./Iterators.md), onde podemos trabalhar com um grande volume de dados, mas apenas um por vez é carregado na memória (diferente do que acontece em uma [lista](./List.md) por exemplo).

A diferença é que os `Generators` não são objetos como os iterators, elas na verdade são funções capazes de pausar, que podem retornar um valor diferente a cada chamada. As pausas são atríbuidas a palavra reservada `yield`. 

Para utilizar o `Generator` tem de se criar a função, atribuir a função a uma variável, e então realizar a chamada do método `next()`. A cada chamada, será devolvido o valor do próximo `yield`. 

```python
def fun():
    yield 1
    yield 2
    yield 3

result = fun()

print(next(result))
print(next(result))
print(next(result))
```

Segue uma aplicação mais comum do `Generator` dentro de um laço [for](./For.md). Assim como com os iterators, o `generator` não precisa invocar o `next()` dentro do laço.

```python
def fun(max):
    cnt = 1
    while cnt <= max:
        yield cnt
        cnt += 1

ctr = fun(5)
for n in ctr:
    print(n)
```