<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [if / elif / else](./ifElifElse.md)

# if / elif / else

Durante a execução do nosso script é comum querermos manipular o fluxo de execução, ou que certas coisas só aconteçam em determinadas situações, é para isso que serve a estrutura **if / else**.

O **if / else** funciona da seguinte maneira: o Python avaliará a condição do if, e se verdadeiro, executará o código de dentro do if, caso seja falso, executará o else. Lembrando que a presença do else é opcional. Segue exemplo:

O Python não utiliza blocos como linguagens como [Javascript](../Javascript/Index.md), ao invés disso é necessário usar um **:** com o bloco interno separado por **tab**. 

Segue exemplo de um if / else:

```python
idade: int = 15

if(idade < 18):
    print("Não pode beber")
else :
    print("Pode beber")
```

Exemplo de if sem um else: 

```python
nome: str = "Mathias"

if(nome == "Mathias"):
    print("Seu nome é Mathias")
``` 

Pode haver casos onde queremos ter mais de duas opções de resultados. para isso podemos utilizar o **elif**.

```python
comida: str = "sushi"

if comida == "pizza":
    print("Ótima escolha! Quem não ama pizza? 🍕")
elif comida == "sushi":
    print("Um clássico sofisticado! 🥢")
elif comida == "hamburguer":
    print("Rei ou rainha do fast food! 🍔")
elif comida == "salada":
    print("Saudável, hein? Mas onde está o gosto pela vida? 🥗")
elif comida == "chocolate":
    print("Apoio emocional comestível. Respeito total! 🍫")
else:
    print(f"Hmm... {comida}? Não conheço, mas se faz feliz, tá valendo! 😋")
```