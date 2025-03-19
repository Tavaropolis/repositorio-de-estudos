<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Internings](./Id.md)

# Internings

O interning em [Python](./Index.md) é uma otimização que ocorre internamente para evitar a criação desnecessária de múltiplos objetos idênticos na memória. 

## String Interning
O Python mantém um cache interno de algumas strings imutáveis, especialmente as que:

- São pequenas (geralmente ≤ 20 caracteres).
- Contêm apenas letras, números e underscores `(_)`.
- São criadas em tempo de compilação e não geradas dinamicamente.

Isso significa que se você criar múltiplas strings idênticas, elas podem compartilhar o mesmo espaço na memória em vez de criar novos objetos.

```python
a = "hello"
b = "hello"

print(id(a) == id(b))  # True, ambas apontam para o mesmo objeto!
```

Quando a string é criada dinâmicamente o comportamento é meio imprevisível.
```python
x = "py" + "thon"
y = "python"
print(id(x) == id(y))  # Pode ser False, pois x foi criado dinamicamente
```

## Integer internings
Python reutiliza inteiros no intervalo de -5 a 256, pois são usados frequentemente:

```python
x = 100
y = 100
print(id(x) == id(y))  # True (inteiro dentro do cache)

x = 257
y = 257
print(id(x) == id(y))  # False (inteiro fora do cache)
```

## Tuple internings
Se uma tupla contém apenas valores imutáveis, pode ser internada. Mas se a tupla for maior ou contiver elementos mutáveis, pode ter IDs diferentes.

```python
t1 = (1, 2, 3)
t2 = (1, 2, 3)
print(id(t1) == id(t2))  # Pode ser True (tupla pequena e imutável)
```