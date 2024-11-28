<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [continue](./Continue.md)

# continue

O **continue** é uma das palavras reservadas do python. Ela serve para ser utilizada dentro de  um laço de repetição ([while](./While.md) ou [for](./For.md)). Uma vez que o **continue** acionado, o programa pula aquela iteração e parte para a próxima. 

No exemplo abaixo, assim que a variável i for igual a 3, o while irá pular para próxima iteração, ignorando todo o código abaixo.
```python
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```

Exemplo de **continue** dentro de um laço for:

```python
comidas = ["pizza", "sushi", "brocolis", "hamburguer", "chocolate"]

print("Comidas da festa:")
for comida in comidas:
    if comida == "brocolis":
        print(f"🤢 Pulando o {comida}, ninguém quer isso na festa!")
        continue  # Pula o brócolis e vai para o próximo item
    print(f"😋 {comida.capitalize()} está no menu!")

"""Saída no terminal
Comidas da festa:
😋 Pizza está no menu!
😋 Sushi está no menu!
🤢 Pulando o brocolis, ninguém quer isso na festa!
😋 Hamburguer está no menu!
😋 Chocolate está no menu!
"""
```