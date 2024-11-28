<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [break](./Break.md)

# break

O **break** é uma palavra reservada do python usanda em laços de repetição (assim como o [continue](./Continue.md)). Quando o código chega no **break**, o laço de repetição é imediatamente interrompido.

```python
paciência = 5

while True:
    print("Ainda aguento mais um pouco... 😤")
    paciência -= 1
    if paciência == 0:
        print("Chega! Perdi a paciência. 😡")
        break

"""retorno do terminal
Ainda aguento mais um pouco... 😤
Ainda aguento mais um pouco... 😤
Ainda aguento mais um pouco... 😤
Ainda aguento mais um pouco... 😤
Ainda aguento mais um pouco... 😤
Chega! Perdi a paciência. 😡
"""
```

Exemplo de **break** em um laço for: 

```python
ilha = ["areia", "pedra", "coqueiro", "tesouro", "crab"]

for item in ilha:
    if item == "tesouro":
        print("🏴‍☠️ Achei o tesouro! Parando a busca!")
        break
    print(f"⛏️ Vasculhando {item}... Nada aqui.")

"""retorno no terminal
⛏️ Vasculhando areia... Nada aqui.
⛏️ Vasculhando pedra... Nada aqui.
⛏️ Vasculhando coqueiro... Nada aqui.
🏴‍☠️ Achei o tesouro! Parando a busca!
"""
```