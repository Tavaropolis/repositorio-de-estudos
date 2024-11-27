<link rel="stylesheet" type="text/css" href="../../CSS/dark-theme.css">

[Anotações](../../) > [Linguagens](../Index.md) > [Anotações Python](./Index.md) > [input()](./Input.md)

# input()

Inicialmente quando estamos iniciando em uma linguagem nova, nossos programas são simples e rodam inteiramente no terminal. Além do **print()** para exibir mensagens ao usuário, porém é possível também receber informações do usuário através da função **input()**.

**input()** funciona da seguinte forma, o programa fica "congelado", esperando que o usuário digite alguma coisa e aperte enter. O texto digitado pelo usuário pode ser salvo em uma variável e reutilizado mais tarde. 

Podemos ainda passar uma string como parâmetro para o **input()**, para que uma mensagem seja exibida guiando o usuário.

```python
cor = input("Digite sua cor favorita: ")
animal = input("Digite um animal: ")

print(f"Seu nome de dragão é: {cor.capitalize()}{animal.capitalize()} o Terrível!")
```

Lembrando que os dados do usuário sempre vem como string, mesmo que o usuário tenha digitado um número.

```python
resposta = input("Digite um número qualquer: ")

print(f"Você digitou '{resposta}' e o Python acha que isso é do tipo {type(resposta).__name__}.") #resposta é um int
```