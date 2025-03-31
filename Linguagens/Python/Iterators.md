<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Iterators](./Iterators.md)

# Iterators

Todas as coleções que tratamos até agora ([listas](./List.md), [tuplas](./Tuple.md), [sets](./Set.md), [dicts](./Dict.md), etc), são considerados no [python](./Index.md) como **`iterables`**. Ou seja, eles podem ser percorridos via loop, e todos os valores estão na memória quando declarados.

Já um **`iterator`** é uma objeto que pode ser criado a partir de um **`iterable`** e possuí os métodos: `__iter()__`  e `__next()__`. 

## Iterator vs Iterable

A grande diferença entre os dois, é que o `iterator` guarda na memória apenas seu valor atual, e o próximo valor, ao contrário dos `iterables` em que todos os valores da lista ficam na memória ao mesmo tempo. Por esse motivo, os `iterators` ocupam menos memória, mas são mais difíceis de se manipular.

É possível ver quantos bytes na memória um objeto ocupa com o método `sys.getsizeof()`:

```python
import sys

list_normal = [x for x in range(10)]
list_iterator = iter([x for x in range(10)])

print(f"list_normal: {sys.getsizeof(list_normal)}") #Saída: list_normal: 184
print(f"list_iterator: {sys.getsizeof(list_iterator)}") #Saída: list_iterator: 48
```

# Manipulando um iterator

Para se criar um iterator basta aplicar o construtor `iter()` em um `iterable`:

```python
list_iterator = iter([x for x in range(10)])
set_iterator = iter({x for x in range(10)})

print(type(list_iterator)) #Saída: <class 'list_iterator'>
print(type(set_iterator)) #Saída: <class 'set_iterator'>
``` 

Para se acessar o próximo valor de um `iterator`, basta utilizar o método `next()`. Ao chegar no último valor o python retornará um erro de StopIteration: 

```python
list_iterator = iter([x for x in range(6)])

print(next(list_iterator)) #Saída: 0 
print(next(list_iterator)) #Saída: 1
print(next(list_iterator)) #Saída: 2
print(next(list_iterator)) #Saída: 3
print(next(list_iterator)) #Saída: 4
print(next(list_iterator)) #Saída: 5
print(next(list_iterator)) #Saída: 6
```

É possível percorrer o `iterator` com um [for](./For.md), implicitamente o python roda um `next()`, já com tratamente de erros quando se chega no último valor:

```python
list_iterator = iter([x for x in range(6)])

for x in list_iterator:
    print(x)

"""
Saída:
0
1
2
3
4
5
"""
```

Se você desejar pode implementar `iterator` em uma [classe](./Class.md). Segue exemplo:

```python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def __next__(self):
    x = self.a
    self.a += 1
    return x

myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
print(next(myiter))
```