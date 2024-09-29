<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [Atribuição Multípla](./Variaveis.md)

# Atribuição Multípla
Atribuir é o ato de definir um valor para uma variável. Um recurso não muito usual, mas que é bem útil e está presente no Python é a atribuição múltipla. Ou seja, em uma mesma linha de código, podemos atribuir valor a mais de uma variável.

```python
a, b, c = "Naruto", "Sasuke", "Sakura"

print(a) #Printa Naruto
print(b) #Printa Sasuke
print(c) #Printa Sakura
```

Com uma pequena mudança na síntaxe, é possível atribuir o mesmo valor para muitas variáveis

```python
a = b = c = "Naruto"

print(a) #Printa Naruto
print(b) #Printa Naruto
print(c) #Printa Naruto
```

Vou falar mais sobre listas e coleções no futuro, mas fica o registro que da para usar atribuições multiplas para desenpacotar listas.

```python
ninjas = ["Naruto", "Sasuke", "Sakura"]
a, b, c = ninjas

print(a) #Printa Naruto
print(b) #Printa Sasuke
print(c) #Printa Sakura
```