<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Str](./Str.md)

# Str

O tipo de dado que comporta texto é comumente chamado de **String**, o Python ele recebe o nome de **Str** mas é exatamente o mesmo conceito. Uma String pode ser declarada com aspas simples ou duplas.

```python
print("Hello")
print('Hello')
```

Pode-se também utilizar aspas triplas para fazer uma string de muitas linhas. Essas aspas podem ser tanto duplas quanto simples

```python
a = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""

b = '''Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua.'''

print(a)
print(b)
```

Além disso Strings são objetos iteravéis, ou seja podemos selecionar caracteres pelo índice e porcerrer com laços de repetição como [for](./For.md) e [while](./While.md).

```python
a = "Hello, World!"
print(a[1]) #Saída e
```

```python
for x in "banana":
  print(x)

""" Saída do print
b
a
n
a
n
a
"""
```
